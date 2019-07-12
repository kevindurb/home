FROM gliderlabs/logspout

RUN apk add --update go build-base git mercurial ca-certificates
RUN mkdir -p /go/src/github.com/gliderlabs
COPY ./modules.go /src/modules.go
RUN cp -r /src /go/src/github.com/gliderlabs/logspout
WORKDIR /go/src/github.com/gliderlabs/logspout
ENV GOPATH=/go
RUN go get
RUN go build -ldflags "-X main.Version=$1" -o /bin/logspout
RUN apk del go git mercurial build-base
RUN rm -rf /go /var/cache/apk/* /root/.glide

# backwards compatibility
RUN ln -fs /tmp/docker.sock /var/run/docker.sock
