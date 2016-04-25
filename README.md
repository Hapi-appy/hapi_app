## Hapi-appi

This is a single resource app that uses a server side framework (Hapi), Mongoose, MongoDB to enact basic CRUD and REST to GET, PUT, PATCH and DELETE content in a database.

## Dev-Dependencies
*Chai
*Chai-http
*gulp
*gulp-eslint
*gulp-mocha
*Mocha

## Dependencies
*Hapi
*Mongoose

*Httpie*
*in command line only


####Install dependencies
```
npm install
```


## Setup

###To run:

 You need to use mongod to run this application. See [mongod documentation](https://docs.mongodb.org/manual/reference/program/mongod/) for installation and use.


####In the first terminal activate the mongod daemon to sync with the data directory in the project:

```
mongod --dbpath=./data
```

  <em>This starts the mongod deamon and will run in the background.</em>



####In the second terminal activate app through index:

```
node index
```

  <em>This starts up the server.</em>


####In a third terminal run your httpie REST commands to create content for your database:
Use [httpie](https://github.com/jkbrzt/httpie)

###POST
```
http POST localhost:5000/api/put name=Shirley instrument=violin actor='Karen Scott'
```

  <em>This will post a data object to the database created with mongoose.connection.</em>

```
mongoose.connect(process.env.MONGO_URI || 'mongodb://localhost/pf_db')
```
  <em>And will add to the name, instrument and actor properties the values assigned.</em>

###GET
Get all Partridge family members

```
http POST localhost:5000/api/pf
```

###DELETE
Delete family member from database by by finding their specific id and adding to /api/delete/<id>

```
http POST localhost:5000/api/delete/{pfId}
```

## To Test

```
npm test
gulp
```
