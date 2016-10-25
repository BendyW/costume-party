# costume-party
##1. SQL Commands for Creating Database + User
We create a db for every project and a specific user in the db for that project. This is for security purposes.
```
create database costume_party;
create user 'prodba'@'localhost' identified by 'yellowpencil';
grant all privileges on costume_party.* to 'prodba'@'localhost';
```

##2. Environment Variables
Our environment variables are stored in .env but may also be declared as needed.
```
DB_USER=prodba
DB_PWD=yellowpencil
DB_NAME=costume_party
DB_TYPE=mysql
DB_SERVER=localhost
```

##3. Database Connection
A database connection is defined inside of db.js. It contains all code needed to connect to MySQL.

```
// ./models/db.js
'use strict';

//loads environment variables from .env
require('dotenv').config();

//knex is a database adapter for node
//npm install knex && npm install lodash
//lodash us a dependency of knex
var db = require('knex')({
    client: process.env.DB_TYPE,
    connection: {
        host: process.env.DB_SERVER,
        user: process.env.DB_USER,
        password: process.env.DB_PWD,
        database: process.env.DB_NAME
    }
});

module.exports = db;
```