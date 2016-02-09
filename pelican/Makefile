date=$(shell date +%Y%m%d)
image_name=marcmillien/pelican

all: build version

build:
	docker build -t $(image_name):latest .

version:
	docker tag -f $(image_name):latest $(image_name):$(date)

push:
	docker push $(image_name):latest
	docker push $(image_name):$(date)
