# Unit I: Introduction to Django — Complete Study Guide

This document covers all concepts, theoretical foundations, file structures, and practical commands learned in **Unit I** of the INT253 Django course.

---

## 📌 1. Theoretical Foundations & Core Concepts

### What is Django?
Django is a high-level Python web framework that encourages rapid development and clean, pragmatic design. It follows the **MVT (Model-View-Template)** architectural pattern and comes with a "batteries-included" philosophy, providing built-in features like an admin panel, authentication, and database ORM out of the box.

### Projects vs. Apps
* **Project (`intro_project`)**: The entire collection of configurations, settings, and general architecture for a website. A project can contain multiple apps.
* **App (`core_app`)**: A self-contained module or feature component designed to do a specific job (e.g., user profiles, blog posts, product catalog). This modularity allows code to be reusable across different projects.

### Virtual Environments (`venv`)
* **Definition**: An isolated, self-contained sandbox environment for Python projects.
* **Why we use it**: It prevents dependency conflicts by isolating packages per project, keeping the global operating system clean and making deployments predictable via `requirements.txt`.

### Migrations
* **Definition**: Django’s system for translating your Python code (models/classes) into database instructions (SQL tables and schemas).
* **How it works**: 
  1. `python manage.py makemigrations`: Generates blueprint script files based on model changes.
  2. `python manage.py migrate`: Applies those blueprints to actually build or update tables in the database (SQLite by default).

---

## 🗂️ 2. Project File Structure & Explanation

When you create a project and app, Django generates a specific tree of files. Here is what each one does:

```text
INT253-Django-Course/
└── Unit-01/
    ├── intro_project/         # Outer container folder
    │   ├── manage.py          # Command-line utility tool for project management
    │   └── intro_project/     # Inner project Python package
    │       ├── __init__.py    # Tells Python this directory is a package
    │       ├── settings.py    # Project control panel (database config, installed apps, middleware)
    │       ├── urls.py        # URL table of contents (maps web routes to views)
    │       ├── asgi.py        # Entry point for asynchronous web servers (WebSockets)
    │       └── wsgi.py        # Entry point for traditional synchronous web servers
    └── core_app/              # Your custom modular app folder
        ├── __init__.py
        ├── admin.py           # Register models for the built-in Django Admin panel
        ├── apps.py            # App-specific configuration settings
        ├── migrations/        # Folder holding database migration blueprint scripts
        ├── models.py          # Where database schemas are written as Python classes
        ├── tests.py           # Automated unit testing suite for the app
        └── views.py           # Where request handling logic and HTTP responses are defined


## 📌 Concepts Covered
- **Projects vs. Apps**: A project is the whole website configuration, while an app is a modular, self-contained feature component.
- **Virtual Environment (`venv`)**: An isolated sandbox for Python dependencies to prevent version conflicts globally.
- **Migrations**: The translation layer between Python classes (models) and actual database tables (SQL).

## 🛠️ Key Commands Used
- Create virtual environment: `python3 -m venv venv`
- Activate virtual environment: `source venv/bin/activate`
- Start a Django project: `django-admin startproject <project_name>`
- Create a Django app: `python manage.py startapp <app_name>`
- Run development server: `python manage.py runserver`
- Apply database migrations: `python manage.py migrate`