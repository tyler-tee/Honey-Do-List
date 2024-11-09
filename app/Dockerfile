# Use an official Python runtime as a base image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy requirements.txt first and install dependencies
# Using requirements.txt helps leverage Docker's layer caching
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire project into the working directory
COPY . .

# Expose the port that Flask will run on
EXPOSE 5000

# Set environment variables
# - FLASK_APP tells Flask which app to run
# - FLASK_RUN_HOST and FLASK_RUN_PORT specify host and port for Flask
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
ENV FLASK_RUN_PORT=5000

# Run the application
CMD ["flask", "run"]
