# Race detector not working with Alpine

https://github.com/golang/go/issues/14481

```
$ docker run --rm \
    -v ${PWD}:/go/src/github.com/storz/sandbox/race-detector-not-working-with-alpine \
    golang:1.10.0-alpine \
    go test -v -race ./...

$ docker run --rm \
    -v ${PWD}:/go/src/github.com/storz/sandbox/race-detector-not-working-with-alpine \
    -e CGO_ENABLED=0 \
    golang:1.10.0-alpine \
    go test -v -race ./...
```

```
$ docker build -t golang-alpine-gcc .

$ docker run --rm \
    -v ${PWD}:/go/src/github.com/storz/sandbox/race-detector-not-working-with-alpine \
    golang-alpine-gcc \
    go test -v -race ./...
```
