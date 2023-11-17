run: build
	mkdir -p data
	docker run -d -it \
		--name 389ds \
		--user 1000:1000 \
		-e DS_SUFFIX_NAME="dc=homelab,dc=internal" \
		--network host \
		-v ./data:/data \
		-v ./ldif:/ldif \
		389ds:latest

build:
	docker build -t 389ds:latest .

exec:
	docker exec -it 389ds bash

clean:
	docker stop 389ds || true
	docker rm 389ds || true
	rm -rf data
