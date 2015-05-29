---
layout: post
title: "Testing CORS headers with RSpec and Rack in Rails"
date: 2015-05-19 01:16:17 +0100
comments: true
categories: git
published: true
---

I've not found any blog post or article about how to easily test CORS support implemented in a [Rack](http://rack.github.io/) middleware (e.g. using the [rack-cors](https://github.com/cyu/rack-cors) gem) with RSpec in Rails. So, after figured out I decided to write some small tips I learned from it.

I assume you have a fairly updated Rails app, I tested it with Rails 4.2.x, with `RSpec` tests support, and you want to add support for `CORS` headers.

##Install rack-cors gem

it's better to follow the gem instructions (you'll find the most updated instructions there) than a blog post, but anyway here's how I did it:

Add this to your `Gemfile`:
```sh
gem 'rack-cors', :require => 'rack/cors'
```

Add this to your `config/application.rb`:
```ruby
config.middleware.insert_before(0, "Rack::Cors", logger: (-> { Rails.logger })) do
  allow do
    origins '*'
    resource '*', headers: :any, methods: [:get, :post, :patch, :options]
  end
end
```
These are the common options, tune it to your needs. Here we're allowing requests from any domain for the `get`, `post`, `patch` and `options` methods. `options` is a special method used for [preflight](http://www.nczonline.net/blog/2010/05/25/cross-domain-ajax-with-cross-origin-resource-sharing/) requests.

That's it. `CORS` is now active in this Rails app. Every time we send a request with the `CORS` headers, we'll receive the `CORS` response headers.

##How to test it with cURL

With [cURL](http://curl.haxx.se/), it's easy to test `CORS`. Let's see the most common scenarios:

####Sending the `Origin` header:

* `-H`: Header to include in the request.
* `-I`: Fetch the `HTTP` header only.

```sh
curl -H "Origin:*" -I http://localhost:3000/people/1234
```
We should receive: `Access-Control-Allow-Origin: *`.

####Sending the preflight options method:

Send a options request with `Origin: *`, `Access-Control-Request-Method: get` and `Access-Control-Request-Headers: test`.
* `-X`: Specifies a custom request method
```sh
curl -X OPTIONS -I http://localhost:3000 -H 'Origin: *' -H 'Access-Control-Request-Method: GET' -H 'Access-Control-Request-Headers: test'
```
We should receive `Access-Control-Allow-Origin: *`, `Access-Control-Allow-Methods: get, post, patch, options`, and `Access-Control-Allow-Headers: test`.

##How to test it with `RSpec`

It's a bit tricky to test it with `RSpec`, because we don't have a real server (like [Webrick](https://github.com/nahi/webrick), [Unicorn](http://unicorn.bogomips.org/) or [Puma](https://github.com/puma/puma)) between the code and the client. This usually is not a problem but it does affect in this particular case, and the [rfc3875](https://tools.ietf.org/html/rfc3875#section-4.1.18) explains why. The server translate the custom `HTTP` request headers in this way:

* Convert to upper case.
* Replace `-` with `_`
* Prepend `HTTP_`.

Because we don't have the server to do it for us, we must do it manually. For example, the `Origin` becomes `HTTP_ORIGIN` and `Http-Access-Control-Request-Method` becomes `HTTP_ACCESS_CONTROL_REQUEST_METHOD`.
Let's see some example tests:

####Sending the Origin header:

```ruby
scenario 'Returns the response CORS headers' do
  get '/people/1234', nil, 'HTTP_ORIGIN' => '*'

  expect(last_response.headers['Access-Control-Allow-Origin']).to eq('*')
end
```
####Sending the preflight options method:
```ruby
scenario 'Send the CORS preflight OPTIONS request' do
  options '/', nil, 'HTTP_ORIGIN' => '*', 'HTTP_ACCESS_CONTROL_REQUEST_METHOD' => 'GET', 'HTTP_ACCESS_CONTROL_REQUEST_HEADERS' => 'test'

  expect(last_response.headers['Access-Control-Allow-Origin']).to eq('*')
  expect(last_response.headers['Access-Control-Allow-Methods']).to eq('GET, POST, PATCH, OPTIONS')
  expect(last_response.headers['Access-Control-Allow-Headers']).to eq('test')
  expect(last_response.headers).to have_key('Access-Control-Max-Age')
end
```
Note: You must use integration tests to be able the test through `rack`. A controller test doesn't trigger `rack`, it's like an unit test for the controller.

Don't forget to uppercase, replace `-` and prepend `HTTP_` to all your custom HTTP headers when testing!
