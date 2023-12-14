# Multi-Stage Dockerfile

# Stage 1: Build Stage
FROM python:3.9-slim AS builder

WORKDIR /app

COPY requirements.txt .

# Update the COPY instruction to explicitly reference the file path
COPY ./requirements.txt /app/

RUN pip install --no-cache-dir -r requirements.txt

# Stage 2: Runtime Stage
FROM python:3.9-slim

WORKDIR /app

COPY --from=builder /app /app

COPY app.py .

CMD ["python", "app.py"]
