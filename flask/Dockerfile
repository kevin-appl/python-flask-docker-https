FROM python:3-slim

# Create new directory /app in container image 
# and set working directory.
WORKDIR /app

# Copy your local code to the working directory.
COPY . ./

# Install dependencies.
RUN pip install --no-cache-dir -r requirements.txt

# Run gunicorn webserver and flask app on container startup.
# Number of workers should match your number of available CPU cores.
CMD exec gunicorn --bind 0.0.0.0:8080 --workers 1 --threads 8 main:app

