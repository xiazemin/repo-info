## `spiped:latest`

```console
$ docker pull spiped@sha256:169a4d1d08a242a38595169aaaa83bea5ad2c90909efb442b3f5b8ccefacbbf7
```

-	Platforms:
	-	linux; amd64

### `spiped:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.0 MB (57038623 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:50b2f340e483ffe47645f35eefb50de8de73b0a9685c56ad9a3ed2a8b7669158`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Tue, 25 Apr 2017 05:44:28 GMT
RUN groupadd -r spiped &&	useradd -r -g spiped spiped
# Tue, 25 Apr 2017 05:44:37 GMT
RUN apt-get update &&	apt-get install -y libssl1.0.0 --no-install-recommends &&	rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 05:44:38 GMT
ENV SPIPED_VERSION=1.5.0
# Tue, 25 Apr 2017 05:44:38 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.5.0.tgz
# Tue, 25 Apr 2017 05:44:39 GMT
ENV SPIPED_DOWNLOAD_SHA256=b2f74b34fb62fd37d6e2bfc969a209c039b88847e853a49e91768dec625facd7
# Tue, 25 Apr 2017 05:44:40 GMT
COPY file:0f26a499fef90f06070551ff66a17abfb7e814a4f023905e52236c31b216a7bb in /0001-Fix-docker-stop-issue.patch 
# Tue, 25 Apr 2017 05:45:09 GMT
RUN buildDeps='libssl-dev gcc make curl ca-certificates patch' &&	apt-get update && apt-get install -y $buildDeps --no-install-recommends &&	rm -rf /var/lib/apt/lists/* &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	patch -p1 -d /usr/local/src/spiped/ < /0001-Fix-docker-stop-issue.patch &&	make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apt-get purge -y --auto-remove $buildDeps
# Tue, 25 Apr 2017 05:45:10 GMT
VOLUME [/spiped]
# Tue, 25 Apr 2017 05:45:10 GMT
WORKDIR /spiped
# Tue, 25 Apr 2017 05:45:12 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Tue, 25 Apr 2017 05:45:12 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 25 Apr 2017 05:45:13 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dd94e8692b6cd6ad1d03e61b381a318004f2f11747fe09ae76f7131858d06f34`  
		Last Modified: Tue, 25 Apr 2017 22:01:40 GMT  
		Size: 2.1 KB (2059 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7846e5b09cf9fcc73403b1aecd1966f9d245b2a04ef001f04cca8939cf6213f9`  
		Last Modified: Tue, 25 Apr 2017 22:01:37 GMT  
		Size: 1.8 MB (1804459 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b03f90117766b2522f3fb16f83f69054c023ed24522fc9e0a272671de6d9ee4`  
		Last Modified: Tue, 25 Apr 2017 22:01:37 GMT  
		Size: 1.2 KB (1233 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b7f9dd425f2839047712270146b6d8cb6cb17e750a823454d9024194331e3b7`  
		Last Modified: Tue, 25 Apr 2017 22:01:37 GMT  
		Size: 2.7 MB (2680157 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c2b758f73174c839a124d610188603625d2b344ba0bf2f8c34861ece1949e8db`  
		Last Modified: Tue, 25 Apr 2017 22:01:37 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f7e5d7aad448213e60649e00a520f799c1d1e0e788161f3fcfad4c99d4455f2f`  
		Last Modified: Tue, 25 Apr 2017 22:01:36 GMT  
		Size: 344.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
