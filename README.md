# django-rest-react-tests

Django React project structure with tests

Please read
This post dates back originally to 2019. Two years in modern web development are equal to an eon. The approach outlined here is not inherently bad, but it could fall short for larger teams, and due to potential breaking changes in webpack and the related tooling, it can become hard to keep up with changes. Frameworks like Next.js are a more solid choice for building complex React projects these days.

Django REST with React: what you will learn
In the following tutorial you'll learn:

how to build a simple Django REST API
how to structure a Django project with React
Django REST with React: requirements
To follow along with the tutorial you should have:

a basic understanding of Python and Django
a basic understanding of JavaScript (ECMAScript 2015) and React
a newer version of Node.js installed on your system

### Credit:

- Valentino Gagliardi


# Command line inputs:

### back-end:

- $ mkdir django-react && cd $_  # Creates a new folder and moves into it.
- python -m venv .venv  # Creates a new python virtual environment.
- source .venv/bin/activate # Activates the virtual env (.venv).
- pip install djangorestframework  # Installs the django-rest-framework.
- pip install coverage  # Install the coverage meter for testings.
- django-admin startproject django_react  # Creates and starts the django_react project.
- django-admin startapp leads  # Creates and starts the leads app.
- pip freeze > requirements.txt  # Save the requirements into a .txt file.

### front-end:

- python manage.py startapp frontend  # Creates and starts the frontend app.
- mkdir -p ./frontend/src/components  # Prepares a directory structure for holding React components...
- mkdir -p ./frontend/{static,templates}/frontend  # ... and also static files.
- cd ./frontend && npm init -y  # Moves into the frontend folder and initialize the environment.
- npm i webpack webpack-cli --save-dev  # Installs webpack and webpack cli, then in package.json:

"scripts": {
    "dev": "webpack --mode development --entry ./src/index.js --output-path ./static/frontend",
    "build": "webpack --mode production --entry ./src/index.js --output-path ./static/frontend"
},

- npm i @babel/core babel-loader @babel/preset-env @babel/preset-react --save-dev  # Installs babel for transpiling our code.
- npm i react react-dom --save-dev  # Pulls in React
- npm run dev

... and finally and once again:
- if you're in ./frontend directory: $ python ../manager.py runserver


# Testing tips of what to do and also what NOT to do:

- There's no point in testing neither a vanilla Django model nor the Django ORM. Here's a good starting point for testing in Django:

do not test Django built-in code (models, views, etc)
do not test Python built-in functions
Do not test what is already tested! So what should I test? Have you added a custom method to a Django model? Test it! Do you have a custom view? Test it! But, how do I know what to test exactly?

Do yourself a favour. Install coverage, then, every time you add some code to your application run coverage with:

- coverage run --source='.' manage.py test

Then:

- coverage html  # Generates the report on a .html format
- coverage report  # Sees it on a generated .coverage file and some output on the terminal.
 
  Find out more on testings clicking on the testing-django link in the References section below!


# References:

- https://www.valentinog.com/blog/drf/  # Django REST with React (and a sprinkle of testing)
- https://docs.djangoproject.com
- https://www.django-rest-framework.org
- https://www.valentinog.com/blog/testing-django/
- https://reactjs.org/