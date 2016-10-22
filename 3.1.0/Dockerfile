FROM ubuntu:16.04

# Downloaded from https://github.com/google/protobuf/releases/tag/v3.1.0
# VERSION 3.1.0
COPY bin/protoc /usr/local/bin/
COPY include/google /usr/local/include/

# Built using:
#  go version go1.7 darwin/amd64
#  git clone https://github.com/golang/protobuf
#  cd protobuf/protoc-gen-go
#  git rev-parse HEAD
#  > 98fa357170587e470c5f27d3c3ea0947b71eb455
#  GOOS=linux GOARH=amd64 go build
COPY bin/protoc-gen-go /usr/local/bin/

