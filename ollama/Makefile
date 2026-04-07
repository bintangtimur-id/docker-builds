.PHONY: all build push pull clean help

DOCKER_TAG := bintangtimurid/ollama:latest
BASE_IMAGE := alpine/ollama

all: clean pull build push

help:
	@echo "Available targets:"
	@echo "  make all    - Clean, pull base, build, and push"
	@echo "  make build  - Build Docker image"
	@echo "  make push   - Build and push Docker image"
	@echo "  make pull   - Pull base image alpine/ollama"
	@echo "  make clean  - Remove Docker image"

pull:
	docker pull $(BASE_IMAGE)

build:
	docker build . -t $(DOCKER_TAG)

push: build
	docker push $(DOCKER_TAG)

clean:
	docker rmi $(DOCKER_TAG) 2>/dev/null || true
