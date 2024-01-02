FROM tiangolo/uvicorn-gunicorn-fastapi:python3.10

# Set the working directory
WORKDIR /app

# Copy the FastAPI application code and requirements.txt
COPY ./todo_api /app
COPY ./requirements.txt /app

# Install Gunicorn (comment this if you want to run directly with uvicorn)
RUN pip install gunicorn 


# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Command to run the application (uncomment if you want run server using uvicorn)
# CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]

# Command to start the application using Gunicorn
CMD ["gunicorn", "main:app", "-k", "uvicorn.workers.UvicornWorker", "-c", "/gunicorn_conf.py"]


# "-k", "uvicorn.workers.UvicornWorker": 
# Specifies the Gunicorn worker class to use (uvicorn.workers.UvicornWorker). 
# This worker class allows Gunicorn to run Uvicorn as a worker.

# "-c", "/gunicorn_conf.py": 
# Specifies the Gunicorn configuration file to use. 
# The /gunicorn_conf.py file is present in the base image and contains default Gunicorn configurations.