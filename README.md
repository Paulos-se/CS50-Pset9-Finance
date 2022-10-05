# cs50 pset9 Finance webb app

## Full-stack web app made with Bootstrap, Flask back-end, and SQLite3 database.

To use this project after you forked the repo, you will need to get an API key from [IEX](iexcloud.io/cloud-login#/register/) (free account registration), which lets you download stock quotes via their API (application programming interface) using URLs like https://cloud.iexapis.com/stable/stock/nflx/quote?token=API_KEY

With the API, run the following command within an IDE's terminal: $ export API_KEY=API.

Start Flask’s built-in web server:
$ flask run

## This app features

- register, quote, buy, index, sell and history templates with Jinja dynamic content generation
- app.py (lots of routing, logics, and Sqlite3 QUERIES)
- `users`and`portfolio` tables to keep track of all stock and transactions by all users. It is stored in finance.db
- requirements.txt to install

## Flask app file structure:

• app.py

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

### Cookie Session in Flask

- Session: basically, servers plants cookie (i.e. a saved state, a file, a large number) on your device, to help them remember your identity.
- How it works? BROWSER (if have a cookie) sends cookie along with GET requests, and SERVER: validates, then skip login during same sesson, server personal data, etc.
- ENTER Incognito mode: not employing cookies.

_Callback_: a function that will eventually be called, when it has an answer for you.

### An AJAX call

sends additional HTTP request to server (for chat messages, autocomplete, etc.). So WHEN the response is ready, the callback function would receive the response as its argument.
