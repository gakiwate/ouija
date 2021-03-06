ouija
=====

Failure rate analysis for tbpl.

# Installation

The production ouija server is running on Ubuntu, so this is probably the easiest environment in which to get things running, but other distributions of linux should be fine as well. We use Apache on the production server, but Ouija will run standalone for testing as well.

## Dependencies:
* MySQL
* Python
* MySql-python
* Flask

## Database configuration:
Ouija assumes MySQL has been installed with a root user using the password 'root'. Create the MySQL database using the sql/schema.sql script.

    mysql --user root --password < schema.sql
    
Fetch data for the database using the src/updatedb.py script. The delta argument controls how many days worth of data need to be fetched. Two should be sufficient to get started.

    python updatedb.py --delta 2

## Start the app
Start the application:

    cd src
    python server.py

You should see ouija running at http://localhost:8314/index.html.
