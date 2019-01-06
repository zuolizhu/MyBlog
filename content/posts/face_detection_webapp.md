---
title: "Face Detection Webapp"
author: "Zuoli Zhu"
tags: ["React", "JavaScript", "PostgreSQL", "Clarifai"]
categories: ["Software Development"]
date: 2019-01-05T22:47:26-05:00
---

A simple web application using the [Clarifai API](https://clarifai.com/) to detect faces on a giving image url. Using the `Express.js` backend server to communicate with the `PostgreSQL` database.



### Screenshots:

![homepage](/images/dev/react/facedetector/mainpage.png)

![singleface](/images/dev/react/facedetector/singlefaceDetection.png)

![multifaces](/images/dev/react/facedetector/multifaceDetection.png)

![signup](/images/dev/react/facedetector/signup.png)

![login](/images/dev/react/facedetector/login.png)



### GIF demo:

![demo](/images/dev/react/facedetector/appdemo.gif)



### Full Project Code:

[Front end github link](https://github.com/zuolizhu/ReactProjects/tree/master/facedetector)

[Back end github link](https://github.com/zuolizhu/ReactProjects/tree/master/facedetector-api)

### Instruction to run this app

To run this web app on your local machine, please make sure the configuration below matches your local setting:

Create the database with `users` table and `login` table, I used `PostgreSQL`:

```sql
CREATE TABLE users (
    id serial PRIMARY KEY,
    name VARCHAR(100),
    email text UNIQUE NOT NULL,
    entries BIGINT DEFAULT 0,
    joined TIMESTAMP NOT NULL
);
```

```sql
CREATE TABLE login (
    id serial PRIMARY KEY,
    hash VARCHAR(100) NOT NULL,
    email text UNIQUE NOT NULL
);
```

To connect backend server with the database:

```javascript
const pgdatabase = knex({
	client: 'pg',
	connection: {
		host: '127.0.0.1',
		user: '{your database username}',
		password: '{your database password}',
		database: '{your database name}'
	}
});
```

Then change the API key setting in backend code `image.js`:

```javascript
const app = new Clarifai.App({
	apiKey: '{your API key}'
});
```

Finally, `npm start` and check your browser :tada:!

