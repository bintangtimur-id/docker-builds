.PHONY: all build push pull clean help

DOCKER_TAG := bintangtimurid/python:latest

all: clean pull build push

help:
	@echo "Available targets:"
	@echo "  make all    - Clean, pull base, build, and push"
	@echo "  make build  - Build Docker image"
	@echo "  make push   - Build and push Docker image"
	@echo "  make pull   - Pull base image python:3.11-slim"
	@echo "  make clean  - Remove Docker image"

pull:
	docker pull python:3.11-slim

build:
	docker build . -t $(DOCKER_TAG)

push: build
	docker push $(DOCKER_TAG)

clean:
	docker rmi $(DOCKER_TAG) 2>/dev/null || true
