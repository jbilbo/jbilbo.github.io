---
title: 'Las 7 diferencias'
date: '2008-01-23'
tags:
- Developer
---

Éstas 2 funciones ruby hacen EXACTAMENTE lo mismo.

Estilo 1:

def register_with_captcha(user, activate_captcha = true)

  activate_captcha ? (user.valid? ? 1 : 0) : (user.save ? 2 : 0)

end

Estilo 2:

def register_with_captcha(user, activate_captcha = true)

  result = 0

  if activate_captcha == true

    if user.valid?

      result = 1

    end

  else

    if user.save

      result = 2

    end

  end

  return result

end