# Stage 1: Build the application
FROM python:3.9-slim as build

# Set the working directory
WORKDIR /app

# Copy the requirements file and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code
COPY . .

# Stage 2: Create the final image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Copy the built application from the previous stage
COPY --from=build /app /app

# Expose the port the application runs on
EXPOSE 3000

# Run the application
CMD ["python", "app.py"]
