clean:
	rm -rf ./log

build: clean
	docker build . -t mesa:24 --no-cache --progress plain > ./log

run:
	docker run --rm -it --name mesa-24 mesa:24