FROM python:3.11-slim

# Set the working directory
WORKDIR /app

COPY requirements/requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir --upgrade -r /app/requirements.txt

COPY ./src /app/src

RUN addgroup --system app && adduser --system --group app
USER app

# Expose the application port
EXPOSE 80

# Run the application
ENTRYPOINT ["uvicorn", "src.main:app", "--host", "0.0.0.0", "--port", "80"]
