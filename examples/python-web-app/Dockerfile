# Use the latest Ubuntu base image
FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy application files
COPY requirements.txt /app/
COPY devops /app/

# Update the package list and install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    # Disable PEP 668 restriction temporarily
    PIP_BREAK_SYSTEM_PACKAGES=1 pip install -r requirements.txt

# Expose the application port
EXPOSE 8000

# Default command to run the application
CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]



