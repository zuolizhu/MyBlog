---
title: "Event Tickets Manager"
author: "Zuoli Zhu"
tags: ["Java", "Spring Boot", "Thymeleaf", "MySQL"]
categories: ["Software Development"]
date: 2018-12-25T22:48:28-05:00
---

This is a team project built with Spring Boot + Thymeleaf + MySQL. HTML theme musica made by [Colorlib](https://colorlib.com/).

I am the team leader worked on prototyping, architecture, UI design, framework, and devops. Currently this project is offline. 

To run this app on your local machine, please config the `application.properties` file to match your setting:

```javascript
spring.jpa.database-platform=org.hibernate.dialect.MySQL5Dialect
spring.jpa.hibernate.ddl-auto=create-drop
spring.datasource.url=jdbc:mysql://localhost:3306/${dbname}
spring.datasource.username=${DB_USER}
spring.datasource.password=${DB_PASSWD}
```

User configuration is located in `UsersLoader.java`:
```java
// Add user role
Role userRole = new Role("ROLE_USER");
roleRepo.save(userRole);
// Add an user
User customer1 = new User("customer1@gmail.com", secret, true);
customer1.addRole(userRole);
userRepo.save(customer);
```

### Screenshots:
![homepage](/images/dev/springboot/eventticketsmanager/homepage.png)
![homepage](/images/dev/springboot/eventticketsmanager/detailpage.png)
