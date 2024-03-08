clean:
	rm -rf ./log

build: clean
	docker build . -t mesa:23 --no-cache --progress plain > ./log

run:
	docker run --rm -it --name mesa-23 mesa:23