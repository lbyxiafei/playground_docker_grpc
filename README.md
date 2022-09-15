[toc]

# Env Setup

```conda activate grpc```

> generate protos:

```python -m grpc_tools.protoc -I./protos --python_out=. --grpc_python_out=. ./protos/helloworld.proto```

# Build & Run

> local build:

```docker build --tag grpc .```

> local run:

```docker run --publish 9999:50051 grpc```

# Config

## HelloWorld

> server port: `50051`