FROM public.ecr.aws/docker/library/python:3.11-slim

WORKDIR /app

RUN apt-get update -y && \
    apt-get install -y build-essential libpq-dev && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip setuptools wheel

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

EXPOSE 5153

# Run the app
CMD ["python", "app.py"]