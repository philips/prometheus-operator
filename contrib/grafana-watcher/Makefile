all: build

FLAGS =
ENVVAR = GOOS=linux GOARCH=amd64 CGO_ENABLED=0
REGISTRY = quay.io/coreos
TAG = v0.0.1
NAME = grafana-watcher

build:
	$(ENVVAR) go build -o ${NAME} main.go

image: build
	docker build -t ${REGISTRY}/${NAME}:$(TAG) .

push: image
	docker push ${REGISTRY}/${NAME}:$(TAG)

clean:
	rm -f ${NAME}

.PHONY: all build image push clean
