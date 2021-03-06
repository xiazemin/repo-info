## `rethinkdb:latest`

```console
$ docker pull rethinkdb@sha256:37bdff38d86611a9cb34e89d70b18618316d17c3c3fa867be316c6ea99e31496
```

-	Platforms:
	-	linux; amd64

### `rethinkdb:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **77.9 MB (77867101 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c5ed876750b40cde4725ea9eb9d8503f4d1419a2f23ac2ef8e4cc1d535e2c3a2`
-	Default Command: `["rethinkdb","--bind","all"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Tue, 25 Apr 2017 04:57:16 GMT
MAINTAINER Daniel Alan Miller <dalanmiller@rethinkdb.com>
# Tue, 25 Apr 2017 04:57:19 GMT
RUN apt-key adv --keyserver pgp.mit.edu --recv-keys 1614552E5765227AEC39EFCFA7E00EF33A8F2399
# Tue, 25 Apr 2017 04:57:20 GMT
RUN echo "deb http://download.rethinkdb.com/apt jessie main" > /etc/apt/sources.list.d/rethinkdb.list
# Tue, 25 Apr 2017 04:57:21 GMT
ENV RETHINKDB_PACKAGE_VERSION=2.3.5~0jessie
# Tue, 25 Apr 2017 04:57:40 GMT
RUN apt-get update 	&& apt-get install -y rethinkdb=$RETHINKDB_PACKAGE_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 04:57:41 GMT
VOLUME [/data]
# Tue, 25 Apr 2017 04:57:42 GMT
WORKDIR /data
# Tue, 25 Apr 2017 04:57:42 GMT
CMD ["rethinkdb" "--bind" "all"]
# Tue, 25 Apr 2017 04:57:43 GMT
EXPOSE 28015/tcp 29015/tcp 8080/tcp
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60f7b9a55bc5fb557f2553e994f4afc58cb505dcbbdd1fad7dd77e16ee5e2626`  
		Last Modified: Tue, 25 Apr 2017 21:21:53 GMT  
		Size: 1.4 KB (1437 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b28f0b951e87815ac357dfe80ebe3d2a1d08010590ba4addef71730f970ef68`  
		Last Modified: Tue, 25 Apr 2017 21:21:53 GMT  
		Size: 213.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e93e40ea6c05844fb9641294c3172398659ff18202112655193a40521e3d182`  
		Last Modified: Tue, 25 Apr 2017 21:24:49 GMT  
		Size: 25.3 MB (25315082 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02e232f10849da118fc5b7db5ebead4ff7b6c23e9f874e17f56fdca5aaac6578`  
		Last Modified: Tue, 25 Apr 2017 21:24:45 GMT  
		Size: 93.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
