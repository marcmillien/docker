date=$(shell date +%Y%m%d)
image_name=marcmillien/debian-arm

all: build version clean

build: debootstrap dockerbuild

debootstrap:
	debootstrap --variant=minbase --arch=armel jessie root

dockerbuild:
	tar -C root/ -c . | docker import - $(image_name):latest

version:
	docker tag -f $(image_name):latest $(image_name):$(date)

push:
	docker push $(image_name):latest
	docker push $(image_name):$(date)

clean:
	rm -rf root.tar.gz root
