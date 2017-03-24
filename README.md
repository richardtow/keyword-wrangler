# sqlite3 is built in
which sqlite3
/usr/bin/sqlite3

# To create the database
$ sqlite3 /var/tmp/keyword-wrangler.test.sqlite

# To delete the sqlite database file
$ rm /var/tmp/keyword-wrangler.test.sqlite

sqlite> CREATE TABLE keyword (id INTEGER PRIMARY KEY, value TEXT, categoryID INTEGER);

sqlite> CREATE TABLE category (id INTEGER PRIMARY KEY, name TEXT);

sqlite> .quit

sqlite> .help


# Start server in dev environment
$ KW_ENV=dev node src/backend/index.js

# Start server in test environment
$ KW_ENV=test node src/backend/index.js


# Run specs in dev environment
$ KW_ENV=dev ./node_modules/.bin/jasmine-node --verbose --captureExceptions ./spec/

# Run specs in test environment
$ KW_ENV=test ./node_modules/.bin/jasmine-node --verbose --captureExceptions ./spec/



# To create migration file, it will programmatically create the 'keyword' & 'catetory' tables
# we already created manually.
$ ./node_modules/.bin/db-migrate create createKeywordAndCategoryTable --env test


# Apply migrations in dev environment
$ ./node_modules/.bin/db-migrate up --env dev

# Apply migrations in test environment
$ ./node_modules/.bin/db-migrate up --env test


# To combine the migration runs with the test runs
$ ./node_modules/.bin/db-migrate up --env test && ./node_modules/.bin/jasmine-node --verbose --captureExceptions ./spec/


# While in folder keyword-wrangler/src/frontend,
# This will install all dependecies into src/frontend/bower_components.
# Run:
$ ../../node_modules/.bin/bower install


# Download WebStorm at Mar 4, 2017.
