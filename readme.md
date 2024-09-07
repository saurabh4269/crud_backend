# Backend System with CRUD Operations, Admin Panel, and Data Entry Interface

This project is a backend system, it provides a robust structure for managing users and their products, with CRUD operations, an admin panel, and a data entry interface. The application is designed to dynamically create product tables for each user and allows for easy management through an admin dashboard.

## Features

- **User Management**: CRUD operations for managing users with different roles.
- **Product Management**: Each user has a unique product table, with full CRUD support for managing their products.
- **Admin Panel**: A web-based admin interface to manage users and products.
- **Dynamic Table Creation**: Automatically create a unique product table for each new user.
- **Built with FastAPI**: A modern, fast (high-performance) web framework for building APIs.

## Technologies Used

- **Python**: Backend logic and API development.
- **FastAPI**: Framework for building APIs.
- **SQLAlchemy**: ORM for database interactions.
- **PostgreSQL**: Relational database management.
- **Uvicorn**: ASGI server for running FastAPI.
- **Jinja2 / FastAPI-Admin**: For the admin panel and user interface.

## Prerequisites

Ensure the following software is installed on your machine:

- Python 3.8+
- PostgreSQL
- Git

## Setup and Installation

### 1. Clone the Repository

```bash
git clone https://github.com/saurabh4269/crud_backend
cd crud_backend
```

### 2. Set Up Virtual Environment

Create and activate a virtual environment:

```bash
python -m venv env
source env/bin/activate
```

### 3. Install Dependencies

Install the required Python packages:

```bash
pip install fastapi uvicorn sqlalchemy psycopg2-binary alembic pydantic fastapi-admin jinja2
```

### 4. Configure PostgreSQL Database

- Create a PostgreSQL database:

  ```sql
  CREATE DATABASE my_database;
  ```

- Update the `DATABASE_URL` in `models.py`:

  ```python
  DATABASE_URL = "postgresql://<username>:<password>@localhost/my_database"
  ```

### 5. Set Up SQLAlchemy Models

Run the script to create the necessary tables in the database:

```bash
python -c "from models import Base, engine; Base.metadata.create_all(bind=engine)"
```

### 6. Run the Application

Start the FastAPI server:

```bash
uvicorn main:app --reload
```

The application will be available at `http://127.0.0.1:8000`.

## API Endpoints

### User Management

- **GET** `/admin/users/` - Retrieve a list of users.
- **POST** `/admin/users/` - Create a new user.
- **PUT** `/admin/users/{user_id}` - Update user details.
- **DELETE** `/admin/users/{user_id}` - Delete a user.

### Product Management (User-Specific)

- **GET** `/admin/products/` - Retrieve a list of products.
- **POST** `/admin/products/` - Add a new product.
- **PUT** `/admin/products/{product_id}` - Update product details.
- **DELETE** `/admin/products/{product_id}` - Delete a product.


---