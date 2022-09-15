[toc]

# Env Setup

```conda activate grpc```

> generate protos:

```python -m grpc_tools.protoc -I./protos --python_out=. --grpc_python_out=. ./protos/helloworld.proto```

# Build & Run

## Dockerfile

> Dockerfile:

```Dockerfile
FROM python:3.7

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

CMD ["python3", "helloworld_server.py"]
```

> local build:

```
docker build --tag grpc .
```

> local run:

```docker run --publish 9999:50051 grpc```

```docker run -dp 9999:50051 grpc```

## docker-compose.yml

> Dockerfile:

```Dockerfile
FROM python:3.7

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

COPY requirements.txt /app/

RUN pip install -r requirements.txt

COPY . /app/
```

> docker-compose.yml

```docker-compose.yml
version: '3.9'

services:
    helloworld-server:
        build: .
        command: >
            sh -c "python helloworld_server.py"
        ports:
            - "9999:50051"
```

# Config

## HelloWorld

> server port: `50051`