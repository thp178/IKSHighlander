# Pre-requisites
npm version 5.0.0 or greater - download from [here](https://www.npmjs.com/get-npm)  
postgres - download from [here](https://www.postgresql.org/download/)


# How to run
(assuming linux-like OS)  
  

### Setup Postgres Database Instance:
```
pg_ctl -D /usr/local/var/postgres start

psql postgres

CREATE DATABASE iks;

CREATE USER iks;

\q
```
Note: it is worthwhile setting up a macro to run
```
pg_ctl -D /usr/local/var/postgres start
```
if you do not want to run postgres on startup of your machine.  
  
Navigate to the /app directory before moving on to the next steps.
### Install necessary packages:
```
npm install
```

### Install knex global cli
```
npm install knex --save
```

### Run Migrations
```
knex migrate:latest
```

Note: if migrations ever don't work, drop all tables in the iks database and rerun the migrations.

### Start application:
```
npm start
```

Navigate to [http://localhost:8000](http://localhost:8000)

# Running Unit Tests

```
npm test
```

This script will start the Karma test runner to execute the unit tests. Moreover, Karma will start
watching the source and test files for changes and then re-run the tests whenever any of them
changes.

Single test:
```
npm run test-single-run
```
