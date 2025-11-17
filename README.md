# FastAPI Starter Kit

A production-ready FastAPI starter template designed to help developers quickly build scalable, maintainable, and versioned APIs.

This project includes a modular structure, database support, middleware, logging, and best practices for building modern web APIs.

## Project Structure Overview

| **Folder / File**       | **Purpose** |
|-------------------------|-------------|
| `app/`                  | Main application package containing all code for the FastAPI app. |
| `app/main.py`           | Entry point of the application; creates FastAPI instance and includes routers. |
| `app/config.py`         | Application configuration and environment variables setup. |
| `app/api/`              | All API endpoints, organized by version (e.g., `v1/`, `v2/`). |
| `app/api/v1/`           | Version 1 of API routes. Add resource routers here (`user.py`, `item.py`). |
| `app/core/`             | Core utilities like security, middleware, logging, and helper functions. |
| `app/models/`           | SQLAlchemy database models. |
| `app/schemas/`          | Pydantic schemas for request validation and response serialization. |
| `app/crud/`             | Database operations (CRUD) for interacting with models. |
| `app/services/`         | Business logic layer, keeping route handlers thin. |
| `app/db/`               | Database session, connection, and setup utilities. |
| `requirements.txt`      | Python dependencies for the project. |
| `Dockerfile`            | Docker configuration for containerizing the app. |
| `docker-compose.yml`    | Optional Docker Compose setup for multi-container environments. |
| `.gitignore`            | Specifies files/folders to ignore in Git (e.g., `.venv`, `.idea`, `.env`). |
| `.env`                  | Environment variables for local development. |
| `.env.example`          | Example environment file for reference. |
| `README.md`             | Project documentation. |


## Features

* Versioned APIs: `/api/v1/` and `/api/v2/` for safe evolution
* Database-ready: SQLAlchemy models, session management, and migrations
* Clean separation of concerns: Routers, services, CRUD, models, schemas
* Middleware support: Logging, CORS, request timing, authentication
* Docker-ready for easy deployment
* Environment variable support with `.env` files
* PyCharm and VSCode friendly structure

## Getting Started

1.  **Clone the repository**

    ```sh
    git clone [https://github.com/safi-io/fastapi-starter-kit.git](https://github.com/safi-io/fastapi-starter-kit.git)
    cd fastapi-starter-kit
    ```

2.  **Use as a template**

    To start a new project without inheriting the Git history:

    ```sh
    # Remove existing Git history (Linux/macOS)
    rm -rf .git
    ```
    ```powershell
    # Remove existing Git history (Windows PowerShell)
    rmdir /s /q .git
    ```

    ```sh
    # Initialize new repository
    git init
    git add .
    git commit -m "Initial commit: project setup"
    
    # Add your remote repository
    git remote add origin <your-new-repo-url>
    git push -u origin master
    ```

3.  **Create a virtual environment**

    ```sh
    python -m venv .venv
    ```

    Activate it:

    ```sh
    # Linux / macOS
    source .venv/bin/activate
    ```
    ```powershell
    # Windows
    .venv\Scripts\activate
    ```

4.  **Install dependencies**

    ```sh
    pip install -r requirements.txt
    ```

5.  **Configure environment variables**

    Create a `.env` file in the root directory:

    ```ini
    DATABASE_URL=sqlite:///./test.db
    SECRET_KEY=your-secret-key
    ```
    Use `.env.example` as a reference.

6.  **Run the app**

    ```sh
    uvicorn app.main:app --reload
    ```
    Open [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) for Swagger UI
    Open [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc) for ReDoc documentation

## Using Versioned APIs

* GET `/api/v1/users/` → List all users
* GET `/api/v1/items/` → List all items
* Add new routes in `app/api/v1/` or `app/api/v2/` as your API evolves

**Tip:** Always use versioning to avoid breaking existing clients.

## Middleware and Logging

This template supports:

* Request logging: Logs all incoming requests and responses
* Error logging: Logs exceptions and stack traces
* Request timing: Measures how long each request takes

You can add custom middlewares in `app/core/` as needed.

## Recommended Practices

* Keep business logic in `services/`
* Keep database operations in `crud/`
* Use `schemas` for request/response validation
* Version APIs for breaking changes
* Write tests in a separate `tests/` folder

## Contributing

* Fork the repository
* Create your feature branch (`git checkout -b feature/my-feature`)
* Commit your changes (`git commit -m 'Add feature'`)
* Push to the branch (`git push origin feature/my-feature`)
* Open a pull request

## Author

* LinkedIn: [@safi-io](https://www.linkedin.com/in/safi-io/)
* GitHub: [@safi-io](https://github.com/safi-io)
