---
title: "Warehouse Backend"
author: "Zuoli Zhu"
tags: ["NestJS", "JavaScript", "Backend", "RestAPI"]
categories: ["Software Development"]
date: 2019-03-26T22:42:44-04:00
---

A simple CRUD rest API for warehouse application, built with [Nest](https://github.com/nestjs/nest) framework, and working with cloud mongoDB.



### Instruction to run this app

```bash
$ npm install
```



### Database Configuration

Change the `src/config/keys.ts` file to match your database setting:

```typescript
export default { mongoURI: '' }
```



### Running this backend server

```bash
$ npm run start:dev
```



### Testing with Postman

To add a product into the database, send a `post` request to `http://localhost:3000/products/` with data below:

```json
{
   "productName": "Wood Mouse Pad",
   "description": "Comfortable maple wood made mouse pad",
   "quantity": 70
}
```

![Add A Product](/images/dev/warehouse/post.gif)



To update a product information, for example, to update the quantity of the pillow with its id `5c9adcf4431cb3b3e07feaf3`, just send a `put` request to `http://localhost:3000/products/5c9adcf4431cb3b3e07feaf3` with data:

```json
{
   "quantity": 77
}
```

![Update A Product Info](/images/dev/warehouse/update.gif)



To verify if the quantity of the pillow was updated, send a `get` request with the product id: `http://localhost:3000/products/5c9adcf4431cb3b3e07feaf3`.

![Get A Product Info](/images/dev/warehouse/singleGet.gif)



To remove a product from the database, just send a `delete` request with the product id: `http://localhost:3000/products/5c9adcf4431cb3b3e07feaf3`.

![Remove A Product](/images/dev/warehouse/delete.gif)



### Full Project Code:

[GitHub Link](<https://github.com/zuolizhu/warehouse-backend)