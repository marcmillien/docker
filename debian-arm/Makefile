date = $(shell date +%Y%m%d)
image_name = 'marcmillien/debian-arm'

all: build version clean

build: debootstrap tar dockerbuild

debootstrap:
	debootstrap --variant=minbase --arch=armel jessie root

tar:
	tar -czf root.tar.gz -C root .

dockerbuild:
	docker build -t $(image_name):latest .

version:
	docker tag -f $(image_name):latest $(image_name):$(date)

push:
	docker push $(image_name):latest
	docker push $(image_name):$(date)

clean:
	rm -rf root.tar.gz root
