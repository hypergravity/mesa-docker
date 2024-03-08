clean:
	rm -rf ./log

build: clean
	docker build . -t mesa:7503 --no-cache --progress plain > ./log

run:
	docker run --rm -it --name mesa-7503 mesa:7503