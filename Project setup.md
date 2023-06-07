# Project setup

In the file i will guide you on how to localy run the programs.

## contents
- [Startup order](#startup-order)
    - [Race microservice](#race-microservice)
    - [Unit microservice](#unit-microservice)
    - [Frontend](#frontend)

## Startup order
----------------
## Race microservice 
Requirements
- Have a MongoDB database running with a collection named "races"
- Make sure to add environment variables file (.env) in the root of the project with the following properties:
```sql
# url of the Mongo database
DATABASE_URL = "mongodb://localhost:3600/TOT_RaceManagementDB"
# port where this app will be accessable
PORT = 3500
```
Then run the following commands:
```sql
# install all packages
$ npm install
# then create build
$ npm run build
# then fill database with test data
$ npm run seed

# then start app
$ npm run start
``` 

----------------
## Unit microservice 
Requirements
- Fill in the config.ini with the correct database credentials IMPORTANT: driver property must be 'mysqldb'
- Make sure to add environment variables file (.env) in the root of the project with the following properties:
```sql
not yet implemented
```
Then run the following commands:
```sql
Install python3
# Run the command
$ py -m venv venv
# Activate the venv using the command 
$ venv\Scripts\activate
# Install all requirments
$ pip install -r requirements.txt

# Make sure the venv is active, if not activate it run
$ venv\Scripts\activate
# Start the application 
flask run
``` 

----------------
## Frontend 
Requirements
- Race microservice is running
- Unit microservice is running

Then run the following commands:
```sql
# install all packages
$ npm install
# then create build
$ npm run build

# the start app
$ npm run dev
```
