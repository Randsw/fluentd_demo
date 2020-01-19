# Project namespace: wshihadeh by default
NAMESPACE ?= wshihadeh
# Docker registry
REGISTRY ?= index.docker.io
# Get ruby version
IMAGE := fluentd
IMAGE_TAG ?= 1.0.0

BASE_IMAGE := fluentd-base
BASE_TAG ?= 1.0.0


# Make sure recipes are always executed
.PHONY: build_base build push_base push deploy


# Build and tag Fluentd Docker base image
build_base:
	@echo "Building Fluentd Base Docker Image ..."
	docker build -t ${REGISTRY}/${NAMESPACE}/${BASE_IMAGE}:${BASE_TAG} -f Dockerfile.base .;

# Push fluentd Docker base image
push_base:
	@echo "Push Fluentd Base Docker Image ..."
	docker push ${REGISTRY}/${NAMESPACE}/${BASE_IMAGE}:${BASE_TAG};


# Build and tag Fluentd Docker image
build:
	@echo "Building Fluentd Docker Image ..."
	docker build -t ${REGISTRY}/${NAMESPACE}/${IMAGE}:${IMAGE_TAG} -f Dockerfile .;

# Push fluentd Docker image
push:
	@echo "Push Fluentd Docker Image ..."
	docker push ${REGISTRY}/${NAMESPACE}/${IMAGE}:${IMAGE_TAG};

# Deploy the stack
deploy:
	@echo "Deploy all the services"
	docker stack deploy -c ../docker-stack-fke.yml logging
