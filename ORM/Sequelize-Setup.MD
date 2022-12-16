# Sequelize Set Up # #

## Set Up dotenv ##

The `dotenv` npm package is a simple way to manage environment variables in a Node.js application. Environment variables are key-value pairs that can be used to store sensitive information such as database passwords, API keys, and other secrets that should not be stored directly in your application code.

To use the dotenv package, you first need to install it using npm (the Node.js package manager):

```
npm install dotenv
```

Next, you need to create a file called `.env` in the root directory of your Node.js application. This file should contain your environment variables in the following format:
```
VARIABLE_NAME=variable_value
```

For example, if you have a database password that you want to store as an environment variable, you could add the following line to your `.env` file:
```
DATABASE_PASSWORD=my_secret_password
```

Once you have created your `.env` file and added your environment variables, you can use the dotenv package to load them into your Node.js application. To do this, you need to require the package at the top of your application code and call the `config()` method:

```javascript
require('dotenv').config();
```

This will load the environment variables from your `.env` file into your Node.js application, and you can access them using the `process.env` object. For example, to access the `DATABASE_PASSWORD` variable that we defined earlier, you can use the following code:

```javascript
const password = process.env.DATABASE_PASSWORD;
```

You can then use the password variable in your application code to connect to a database or perform other tasks that require the password.

It is important to note that the `.env` file should not be committed to source control. This is because it contains sensitive information that should not be publicly accessible. Instead, you should add the `.env` file to your `.gitignore` file so that it is not included in your Git repository. This will ensure that your secrets are kept safe and secure.


## Connect to MySQL Database ##

```javascript
const Sequelize = require('sequelize');

// Enable access to .env variables
require('dotenv').config();

// Use environment variables to connect to database
const sequelize = new Sequelize(
  process.env.DB_NAME,
  process.env.DB_USER,
  process.env.DB_PASSWORD,
  {
    host: 'localhost',
    dialect: 'mysql',
    port: 3306
  }
);

module.exports = sequelize
```
This code sets up a connection to a MySQL database using the `Sequelize` library.

The first line imports the `Sequelize` library, which is a popular Node.js library for accessing and querying databases.

The second line requires and loads a module called `dotenv`, which allows the code to access environment variables stored in a file called `.env`. Environment variables are values that are stored outside of the code and can be used to configure the application.

The third line creates a new `Sequelize` instance and establishes a connection to the database. It uses the following four arguments to configure the connection:

* `process.env.DB_NAME`: The name of the database. This value is stored in an environment variable called `DB_NAME`.

* `process.env.DB_USER`: The username for the database. This value is stored in an environment variable called `DB_USER`.

* `process.env.DB_PASSWORD`: The password for the database. This value is stored in an environment variable called `DB_PASSWORD`.

* An object containing the following properties:

    * `host`: The hostname of the database server. In this case, it is set to 'localhost', which means that the database is running on the same machine as the Node.js application.
    * `dialect`: The type of database being used. In this case, it is set to 'mysql', which indicates that the database is a MySQL database.
    * `port`: The port number that the database is listening on. In this case, it is set to 3306, which is the default port for MySQL.  

Finally, the `sequelize` instance is exported using `module.exports` so that it can be used in other parts of the application.