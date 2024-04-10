# Use the official Python image as the base image
FROM python:3.12

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install Flask and its dependencies
RUN pip install flask

# Expose port 5000 to the outside world
EXPOSE 5000

# Define the command to run your Flask application
CMD ["python", "app.py"]