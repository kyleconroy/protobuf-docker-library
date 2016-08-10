# install protobuf from source
# TODO: Create an actual debian package instead of this hot mess of shit
FROM debian:latest

RUN apt-get update && \
    apt-get -y install unzip wget git
RUN wget -q https://github.com/google/protobuf/releases/download/v3.0.0-beta-3/protoc-3.0.0-beta-3-linux-x86_64.zip && \
    mkdir -p protoc-3.0.0 && \
    unzip -q -d protoc-3.0.0 protoc-3.0.0-beta-3-linux-x86_64.zip && \
    mv protoc-3.0.0/protoc /usr/local/bin/ && \
    rm -rf protoc-3.0.0 && \
    rm protoc-3.0.0-beta-3-linux-x86_64.zip

# copied from the golang Dockerfile
ENV GOLANG_VERSION 1.6.3
ENV GOLANG_DOWNLOAD_URL https://golang.org/dl/go$GOLANG_VERSION.linux-amd64.tar.gz
ENV GOLANG_DOWNLOAD_SHA256 cdde5e08530c0579255d6153b08fdb3b8e47caabbe717bc7bcd7561275a87aeb

RUN wget "$GOLANG_DOWNLOAD_URL" -q -O golang.tar.gz \
        && echo "$GOLANG_DOWNLOAD_SHA256  golang.tar.gz" | sha256sum -c - \
        && tar -C /usr/local -xzf golang.tar.gz \
        && rm golang.tar.gz

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"

# Install the Golang codegen plugins
RUN go get -u github.com/golang/protobuf/protoc-gen-go
