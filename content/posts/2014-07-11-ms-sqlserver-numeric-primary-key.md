---
title: MS SQLServer numeric primary key hibernate
date: '2014-07-11'
tags:
- Developer
---

Related to this old hibernate problem: http://grails.1312388.n4.nabble.com/MS-SQLServer-numeric-primary-key-hibernate-td3565392.html

> By default Gorm/hiberate is generating id columns as the numeric(19,0) on SQLServer. I'd like those to be of type BIGINT instead.

The solution is to use the correct dialect for hibernate. In Grails, you can configure it like this:

`grails-app/conf/DataSource.groovy`:

```groovy
dataSource {
    driverClassName = "com.microsoft.sqlserver.jdbc.SQLServerDriver"
    username = "xxx"
    password = "xxx"
    dbCreate = "create-drop" // one of 'create', 'create-drop', 'update', 'validate', ''
    url = "jdbc:sqlserver://host\\instance;databaseName=databaseName"
    dialect = "org.hibernate.dialect.SQLServer2008Dialect"
}
```