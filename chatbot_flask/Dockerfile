# Use a minimal Python 3.10 image
FROM python:3.10-slim

# Set the working directory inside the container
WORKDIR /app

# Copy only requirements file first to leverage Docker layer caching
COPY requirements.txt .

# Upgrade pip to avoid warnings and install dependencies
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Copy the rest of the project files
COPY . .

# Expose the application port (if needed)
EXPOSE 5000

# Set environment variables for Flask
ENV FLASK_APP=app.py
ENV FLASK_ENV=development  

# Run the application
CMD ["python", "app.py"]
