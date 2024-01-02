## Choosing Between Gunicorn and Uvicorn:

### Asynchronous vs. Synchronous:

`Use Uvicorn if your application heavily relies on asynchronous programming and frameworks (e.g., FastAPI, Starlette, etc.).
Use Gunicorn if you are working with synchronous frameworks (e.g., Django, Flask) or need to run mixed synchronous/asynchronous code.
Performance Requirements:

For performance-intensive applications with a high level of concurrency, Uvicorn may provide better performance due to its asynchronous nature.
Gunicorn is still performant and a good choice for many applications, especially those with a mix of synchronous and asynchronous components.
Ease of Use:

Both Gunicorn and Uvicorn are relatively easy to use and well-documented. The choice might come down to personal preference and the specific requirements of your project.
Compatibility:

Gunicorn is widely compatible with various web frameworks and applications.
Uvicorn is specifically designed for ASGI applications and may not be the best choice for synchronous frameworks.`


# Microservice Todo API with FastAPI and Gunicorn

## Overview

This project demonstrates the setup of a microservice for a Todo API using FastAPI, a modern, fast, web framework for building APIs with Python. The microservice is containerized using Docker and utilizes Gunicorn as the production server with Uvicorn workers.

## Features

- **FastAPI:** Utilizes the FastAPI framework for building efficient and modern web APIs with automatic OpenAPI and JSON Schema documentation.

- **Gunicorn with Uvicorn Workers:** Configures Gunicorn to serve the FastAPI application using Uvicorn workers, providing high concurrency and efficient handling of asynchronous code.

- **Dockerized:** The microservice is packaged in a Docker container, ensuring consistent deployment across different environments.

## Project Structure

- **Dockerfile:** Specifies the Docker image configuration, including dependencies and the setup of Gunicorn with Uvicorn workers.

- **gunicorn_conf.py:** Gunicorn configuration file defining settings such as the number of workers and bind address.

- **todo_api/main.py:** Main FastAPI application code for the Todo API.

- **requirements.txt:** Lists the Python dependencies required for the project.

## Getting Started

1. Clone the repository: `git clone https://github.com/your-username/micro-todo-api.git`

2. Build the Docker image: `docker build -t my-fastapi-app .`

3. Run the Docker container: `docker run -d -p 8000:80 --name my-fastapi-container my-fastapi-app`

4. Access the Todo API at `http://127.0.0.1:8000/`

## Dependencies

- FastAPI: v0.103.2
- Gunicorn: Latest version
- Uvicorn: Latest version
- Other dependencies listed in `requirements.txt`


