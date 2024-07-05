# Base image for Python environment
FROM python:3.9

# Set working directory
WORKDIR /app

COPY prestart.sh .

# Install poetry
RUN curl -sSL https://install.python-poetry.org | python3 -


# Install dependencies 
RUN pip poetry install

#Set up the database with the necessary tables
RUN poetry run bash ./prestart.sh

# Copy your application code
COPY . .

# Expose port (adjust if needed)
EXPOSE 65069

# Command to run the application (adjust based on your FastAPI app)
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "65069", "--reload"]