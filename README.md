[toc]

# Env Setup

```conda activate grpc```

> generate protos:

```python -m grpc_tools.protoc -I./protos --python_out=./protos/generated/ --grpc_python_out=./protos/generated/ ./protos/helloworld.proto```

# Build

```docker image build --name grpc -t grpc .```
