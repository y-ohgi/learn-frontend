DOCKER_NODE_IMAGE := node:22-slim

.PHONY: init

init:
	more Makefile

setup: wranger/init

.PHONY: wranger/init
wranger/init:
	docker -it ${DOCKER_NODE_IMAGE} npx wrangler login
