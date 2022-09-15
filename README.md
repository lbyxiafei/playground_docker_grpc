[toc]

# Env Setup

```conda activate grpc```

> generate protos:

```python -m grpc_tools.protoc -I./protos --python_out=. --grpc_python_out=. ./protos/helloworld.proto```

# Build & Run

> local build:

```
docker build --tag grpc .
```

> local run:

```docker run --publish 9999:50051 grpc```

```docker run -dp 9999:50051 grpc```

## Dockerfile

```Dockerfile
FROM python:3.7

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

CMD ["python3", "helloworld_server.py"]
```

## docker-compose.yml

```

```

# Config

## HelloWorld

> server port: `50051`