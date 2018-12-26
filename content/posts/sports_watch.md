---
title: "Sports Watch"
author: "Zuoli Zhu"
tags: ["Java", "Spring Boot", "Thymeleaf", "MySQL"]
categories: ["Software Development"]
date: 2018-12-25T22:59:35-05:00
---

This is a web application built with Spring Boot Thymeleaf and MySQL.

To run this project on your localmachine, please config the `application.properties` file to match your setting:

```javascript
spring.jpa.database-platform=org.hibernate.dialect.MySQL5Dialect
spring.jpa.hibernate.ddl-auto=create-drop
spring.datasource.url=jdbc:mysql://localhost:3306/${dbname}
spring.datasource.username=${DB_USER}
spring.datasource.password=${DB_PASSWD}
```

This project used Facebook Login API

```javascript
FB.init({
    appId      : 'yourappid',
    cookie     : true,
    xfbml      : true,
    version    : 'v3.2'
    });
```

The API server I used for this project is [mysportsfeed](https://www.mysportsfeeds.com/), make sure you have the right setting to fetch the corresponding data:

```java
// API endpoint
String url = "https://api.mysportsfeeds.com/v1.2/pull/nba/2018-2019-regular/team_gamelogs.json?team=" + teamID;
// API access config
String encoding = Base64.getEncoder().encodeToString("{your api user name}:{your api password}".getBytes());

```

### UML Diagram
![UML Diagram](/images/dev/springboot/sportswatch/umldiagram.png)

### Screenshots
![Home Page](/images/dev/springboot/sportswatch/homepage.png)
![Team List](/images/dev/springboot/sportswatch/teamlist.png)
![Admin Panel](/images/dev/springboot/sportswatch/adminpanel.png)
![User Dashboard](/images/dev/springboot/sportswatch/userdash.png)
![Facebook Login](/images/dev/springboot/sportswatch/facebooklogin.png)


### Full Project Link:

[Sports Watch](https://github.com/zuolizhu/SportsWatchWebApp)
