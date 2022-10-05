# cs50 pset9 Finance webb app

## Full-stack web app made with Bootstrap, Flask back-end, and SQLite3 database.

First, you will need to get an API key from [IEX](iexcloud.io/cloud-login#/register/) (free account registration), which lets you download stock quotes via their API (application programming interface) using URLs like https://cloud.iexapis.com/stable/stock/nflx/quote?token=API_KEY

With the API, run the following command within a CS50 IDE's terminal: $ export API_KEY=API.

Start Flask’s built-in web server:
$ flask run

## In this pset, I have implemented:

- App Features: register, quote, buy, index, sell, history
- most of html templates (lots of Jinja dynamic content generation) and their UIs
- app.py (lots of routing, logics, and Sqlite3 QUERIES)
- Design an `portfolio` table to keep track of all stock transactions by all users. It is stored in finance.db

## Flask app file structure:

• application.py

• requirements.txt

• static/

• templates/

## MODEL-VIEW-CONTROLLER (MVC)

design pattern

- model=SQL(..) the database, - view=what user sees, templates,

- controller=application.py, the logics that connect M-V, plus routing

- jinja: Used in HTML templates: {{ var }} , {% block x %} {% endblock %}.

Make use of TEMPLATES: factor out a COMMON layout.html

- {% block body %} {% endblock %}
- in index.html, about.html, etc.: {% extends "layout.html" %} {% block body %} the content {% endblock %}

#### Privacy concern: In dev environment: store personal info in .env files (export username=..., and later retrieve via os.getenv("USERNAME"))

#### Cookie Session in Flask

- Session: basically, servers plants cookie (i.e. a saved state, a file, a large number) on your device, to help them remember your identity.
- How it works? BROWSER (if have a cookie) sends cookie along with GET requests, and SERVER: validates, then skip login during same sesson, server personal data, etc.
- ENTER Incognito mode: not employing cookies.

_Callback_: a function that will eventually be called, when it has an answer for you.

#### An AJAX call: sends additional HTTP request to server (for chat messages, autocomplete, etc.). So WHEN the response is ready, the callback function would receive the response as its argument.

### NOTE for pset9 Finance:

Primary key vs Unique key:

- A primary key is a column of table which uniquely identifies each tuple (row) in that table.
- Primary key will not accept NULL values whereas Unique key can accept one NULL value. (a unique column might have rows with NULL values)
- A table can have only primary key (column), and multiple unique keys (columns).
