VERSION = 6.0.1
MAJOR_VERSION = 6 # AVD follows semantic versioning
REPOSITORY = quay.io/nate_shaw/avd-aap
# docker, podman
RUNTIME = docker

all: build push

build:
	ansible-builder build --container-runtime docker -v 3 --tag ${REPOSITORY}:${VERSION} ${REPOSITORY}:${MAJOR_VERSION}

push:
	${RUNTIME} push ${REPOSITORY}:${VERSION}
	${RUNTIME} push ${REPOSITORY}:${MAJOR_VERSION}
