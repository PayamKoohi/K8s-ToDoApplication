# Use the official Python image as the base image
FROM python:3.10-slim

# Install system dependencies required for psycopg2 and other packages
RUN apt-get update && apt-get install -y \
    libpq-dev gcc \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file into the container
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code into the container
COPY . .

# Expose the port that the app runs on
EXPOSE 5000

# Run the application
CMD ["python", "app.py"]

