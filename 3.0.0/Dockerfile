FROM ubuntu:16.04

# Downloaded from https://github.com/google/protobuf/releases
# VERSION 3.0.0
COPY bin/protoc /usr/local/bin/
COPY include/google /usr/local/include/

# Built using:
#  go version go1.7rc6 darwin/amd64
#  protbuf repo at revision: 2c1988e8c18d14b142c0b472624f71647cf39adb
#    GOOS=linux GOARH=amd64 go build
COPY bin/protoc-gen-go /usr/local/bin/

