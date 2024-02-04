# Node.js Express, Sequelize & PostgreSQL: CRUD Rest APIs

For instruction, please visit:
> [Node.js CRUD Rest APIs with Express, Sequelize & PostgreSQL example](https://bezkoder.com/node-express-sequelize-postgresql/)

We will build Rest Apis that can create, retrieve, update, delete and find Tutorials by title.

The following table shows overview of the Rest APIs that will be exported:

- GET     `api/tutorials`	            get all Tutorials
- GET     `api/tutorials/:id`         get Tutorial by id
- POST    `api/tutorials`             add new Tutorial
- PUT     `api/tutorials/:id`         update Tutorial by id
- DELETE  `api/tutorials/:id`         remove Tutorial by id
- DELETE  `api/tutorials`             remove all Tutorials
- GET     `api/tutorials/published`   find all published Tutorials
- GET     `api/tutorials?title=[kw]`  find all Tutorials which title contains 'kw'

Front-end that works well with this Back-end
> [Axios Client](https://www.bezkoder.com/axios-request/)

> [Angular 8](https://www.bezkoder.com/angular-crud-app/) / [Angular 10](https://www.bezkoder.com/angular-10-crud-app/) / [Angular 11](https://www.bezkoder.com/angular-11-crud-app/) / [Angular 12](https://www.bezkoder.com/angular-12-crud-app/) / [Angular 13](https://www.bezkoder.com/angular-13-crud-example/) / [Angular 14](https://www.bezkoder.com/angular-14-crud-example/) / [Angular 15](https://www.bezkoder.com/angular-15-crud-example/) / [Angular 16](https://www.bezkoder.com/angular-16-crud-example/) / [Angular 17](https://www.bezkoder.com/angular-17-crud-example/)

> [Vue 2 Client](https://www.bezkoder.com/vue-js-crud-app/) / [Vue 3 Client](https://www.bezkoder.com/vue-3-crud/) / [Vuetify Client](https://www.bezkoder.com/vuetify-data-table-example/)

> [React Client](https://www.bezkoder.com/react-crud-web-api/) / [React Redux Client](https://www.bezkoder.com/react-redux-crud-example/)

## Demo Video
This is our Node.js PostgreSQL CRUD example using Express & Sequelize application demo, test Rest Apis with Postman.

[![Node.js PostgreSQL CRUD example Github](http://img.youtube.com/vi/x1pZHN_sjGk/0.jpg)](http://www.youtube.com/watch?v=x1pZHN_sjGk "Node.js PostgreSQL CRUD example Github")

### Test the APIs
Run our Node.js application with command: `node server.js`.

Using Postman, we're gonna test all the Apis above.

- Create a new Tutorial using `POST /tutorials` Api

![node-js-postgresql-crud-example-create](https://dev-to-uploads.s3.amazonaws.com/i/hqvz8ra9p21z927iwzph.png)

After creating some new Tutorials, you can check PostgreSQL table:
```testdb=# select * from tutorials;
 id |    title    |    description    | published |         createdAt          |         updatedAt
----+-------------+-------------------+-----------+----------------------------+----------------------------
  1 | Node Tut #1 | Tut#1 Description | f         | 2020-01-29 10:42:57.121+07 | 2020-01-29 10:42:57.121+07
  2 | Node Tut #2 | Tut#2 Description | f         | 2020-01-29 10:43:05.131+07 | 2020-01-29 10:43:05.131+07
  3 | Node Tut #3 | Tut#3 Description | f         | 2020-01-29 10:43:48.028+07 | 2020-01-29 10:43:48.028+07
  4 | Js Tut #4   | Tut#4 Desc        | f         | 2020-01-29 10:45:40.016+07 | 2020-01-29 10:45:40.016+07
  5 | Js Tut #5   | Tut#5 Desc        | f         | 2020-01-29 10:45:44.289+07 | 2020-01-29 10:45:44.289+07
```

- Retrieve all Tutorials using `GET /tutorials` Api

![node-js-postgresql-crud-example-retrieve-all](https://dev-to-uploads.s3.amazonaws.com/i/m9razjm1njgww58er3as.png)

- Retrieve a single Tutorial by id using `GET /tutorials/:id` Api

![node-js-postgresql-crud-example-retrieve-one](https://dev-to-uploads.s3.amazonaws.com/i/0kuojvc596i5u423od2b.png)

- Update a Tutorial using `PUT /tutorials/:id` Api

![node-js-postgresql-crud-example-update](https://dev-to-uploads.s3.amazonaws.com/i/3buqfz0by0lu2z4kf3uq.png)

Check `tutorials` table after some rows were updated:
```testdb=# select * from tutorials;
 id |     title      |    description    | published |         createdAt          |         updatedAt
----+----------------+-------------------+-----------+----------------------------+----------------------------
  1 | Node Tut #1    | Tut#1 Description | f         | 2020-01-29 10:42:57.121+07 | 2020-01-29 10:42:57.121+07
  3 | Node Tut #3    | Tut#3 Description | f         | 2020-01-29 10:43:48.028+07 | 2020-01-29 10:43:48.028+07
  2 | Node Js Tut #2 | Tut#2 Description | t         | 2020-01-29 10:43:05.131+07 | 2020-01-29 10:51:55.235+07
  4 | Js Tut #4      | Tut#4 Desc        | t         | 2020-01-29 10:45:40.016+07 | 2020-01-29 10:54:17.468+07
  5 | Js Tut #5      | Tut#5 Desc        | t         | 2020-01-29 10:45:44.289+07 | 2020-01-29 10:54:20.544+07
```

- Find all Tutorials which title contains 'js': `GET /tutorials?title=js`

![node-js-postgresql-crud-example-search](https://dev-to-uploads.s3.amazonaws.com/i/u2hbmz5r35o7uo09y3z5.png)

- Find all published Tutorials using `GET /tutorials/published` Api

![node-js-postgresql-crud-example-search-status](https://dev-to-uploads.s3.amazonaws.com/i/dbo753wfqibt0b93d82d.png)

- Delete a Tutorial using `DELETE /tutorials/:id` Api

![node-js-postgresql-crud-example-delete-one](https://dev-to-uploads.s3.amazonaws.com/i/pyos3wq4tchb8ixuyj1c.png)

Tutorial with id=4 was removed from `tutorials` table:
```testdb=# select * from tutorials;
 id |     title      |    description    | published |         createdAt          |         updatedAt
----+----------------+-------------------+-----------+----------------------------+----------------------------
  1 | Node Tut #1    | Tut#1 Description | f         | 2020-01-29 10:42:57.121+07 | 2020-01-29 10:42:57.121+07
  3 | Node Tut #3    | Tut#3 Description | f         | 2020-01-29 10:43:48.028+07 | 2020-01-29 10:43:48.028+07
  2 | Node Js Tut #2 | Tut#2 Description | t         | 2020-01-29 10:43:05.131+07 | 2020-01-29 10:51:55.235+07
  5 | Js Tut #5      | Tut#5 Desc        | t         | 2020-01-29 10:45:44.289+07 | 2020-01-29 10:54:20.544+07
```

- Delete all Tutorials using `DELETE /tutorials` Api

![node-js-postgresql-crud-example-delete-all](https://dev-to-uploads.s3.amazonaws.com/i/ga42747jorssl20ywyug.png)

Now there are no rows in `tutorials` table:
```testdb=# select * from tutorials;
 id | title | description | published | createdAt | updatedAt
----+-------+-------------+-----------+-----------+-----------
```

More Practice:
> [Node.js Express Pagination with PostgreSQL example](https://bezkoder.com/node-js-pagination-postgresql/)

> [Node.js Express File Upload Rest API example](https://bezkoder.com/node-js-express-file-upload/)

> [Node.js Express File Upload with Google Cloud Storage example](https://bezkoder.com/google-cloud-storage-nodejs-upload-file/)

Security:
> [Node.js JWT Authentication & Authorization with PostgreSQL example](https://bezkoder.com/node-js-jwt-authentication-postgresql/)

Associations:
> [Sequelize Associations: One-to-Many Relationship example](https://bezkoder.com/sequelize-associate-one-to-many/)

> [Sequelize Associations: Many-to-Many Relationship example](https://bezkoder.com/sequelize-associate-many-to-many/)

Fullstack:
> [Vue + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/vue-node-express-postgresql/)

> [React + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/react-node-express-postgresql/)

> [Angular 8 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-node-express-postgresql/)

> [Angular 10 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-10-node-express-postgresql/)

> [Angular 11 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-11-node-js-express-postgresql/)

> [Angular 12 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-12-node-js-express-postgresql/)

> [Angular 13 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-13-node-js-express-postgresql/)

> [Angular 14 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-14-node-js-express-postgresql/)

> [Angular 15 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-15-node-js-express-postgresql/)

> [Angular 16 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-16-node-js-express-postgresql/)

> [Angular 17 + Node.js + Express + PostgreSQL example](https://www.bezkoder.com/angular-17-node-js-express-postgresql/)

Integration (run back-end & front-end on same server/port)
> [Integrate React with Node.js Restful Services](https://bezkoder.com/integrate-react-express-same-server-port/)

> [Integrate Angular with Node.js Restful Services](https://bezkoder.com/integrate-angular-10-node-js/)

> [Integrate Vue with Node.js Restful Services](https://bezkoder.com/serve-vue-app-express/)

## Project setup
```
npm install
```

### Run
```
node server.js
```
