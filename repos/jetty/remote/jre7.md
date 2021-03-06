## `jetty:jre7`

```console
$ docker pull jetty@sha256:6a65e5b711942a4df61dfda973b65cc1aac97c029f846d07510a6c815e60bac0
```

-	Platforms:
	-	linux; amd64

### `jetty:jre7` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **160.8 MB (160826795 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f2e66e93c80ed6847e8ad72e38aceb31e3142029d773e4f6019d951aa5d86d23`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 19:54:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:40:05 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:40:06 GMT
ENV LANG=C.UTF-8
# Tue, 25 Apr 2017 00:40:07 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 25 Apr 2017 00:40:08 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64/jre
# Tue, 25 Apr 2017 00:40:09 GMT
ENV JAVA_VERSION=7u121
# Tue, 25 Apr 2017 00:40:09 GMT
ENV JAVA_DEBIAN_VERSION=7u121-2.6.8-2~deb8u1
# Wed, 26 Apr 2017 23:08:46 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$JAVA_HOME" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$JAVA_HOME" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 27 Apr 2017 00:46:50 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Thu, 27 Apr 2017 00:46:51 GMT
ENV JETTY_HOME=/usr/local/jetty
# Thu, 27 Apr 2017 00:46:51 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 27 Apr 2017 00:46:53 GMT
RUN mkdir -p "$JETTY_HOME"
# Thu, 27 Apr 2017 00:46:54 GMT
WORKDIR /usr/local/jetty
# Thu, 27 Apr 2017 00:46:54 GMT
ENV JETTY_VERSION=9.2.21.v20170120
# Thu, 27 Apr 2017 00:46:55 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.21.v20170120/jetty-distribution-9.2.21.v20170120.tar.gz
# Thu, 27 Apr 2017 00:46:56 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D
# Thu, 27 Apr 2017 00:47:01 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -r "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Thu, 27 Apr 2017 00:47:02 GMT
ENV JETTY_BASE=/var/lib/jetty
# Thu, 27 Apr 2017 00:47:03 GMT
RUN mkdir -p "$JETTY_BASE"
# Thu, 27 Apr 2017 00:47:04 GMT
WORKDIR /var/lib/jetty
# Thu, 27 Apr 2017 00:47:06 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules,setuid" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Thu, 27 Apr 2017 00:47:07 GMT
ENV TMPDIR=/tmp/jetty
# Thu, 27 Apr 2017 00:47:09 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Thu, 27 Apr 2017 00:47:10 GMT
COPY file:4f7da2906a90932cfb90db54a45ee08f86b17253747db62085f7512c9efd46ad in / 
# Thu, 27 Apr 2017 00:47:10 GMT
EXPOSE 8080/tcp
# Thu, 27 Apr 2017 00:47:11 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 27 Apr 2017 00:47:12 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e39c3ffe41332a7a3c7f85f57e547361ec90b6e0091dd6058e06acccde2217d4`  
		Last Modified: Mon, 24 Apr 2017 22:19:28 GMT  
		Size: 19.3 MB (19266225 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aac3320edf402163d25e312e38b3611696a39ea8cefb0f58bda4e29bf980ed0a`  
		Last Modified: Tue, 25 Apr 2017 00:50:41 GMT  
		Size: 573.7 KB (573718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16bca657a5b49bc714d81b3e3b0310bcf8d9a48837e8b4acd1fdfd10cfad25e1`  
		Last Modified: Tue, 25 Apr 2017 00:50:40 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:926cca7b89b6a8460b273754a03199a9d998af34a052559c3defe53b15a274c1`  
		Last Modified: Wed, 26 Apr 2017 23:18:35 GMT  
		Size: 78.4 MB (78410775 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:756eef2e790a6ff6eba761712a62a401d0dba04d48d9542cafca2ec9504e5740`  
		Last Modified: Thu, 27 Apr 2017 00:50:15 GMT  
		Size: 2.1 KB (2106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:365412deb22a5515ebbab8059102ada51ab3dec837e42dd11fa41f96291d8083`  
		Last Modified: Thu, 27 Apr 2017 00:50:15 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c4d4005d4e473862f545e9ad57493ef8467d121fc0a1144b7919776f113bdd1`  
		Last Modified: Thu, 27 Apr 2017 00:50:15 GMT  
		Size: 10.0 MB (10020939 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c8ca5ca4dcd12f9a73d657663eab8dad09e8f8b08ffbaf858d97292a60fb313`  
		Last Modified: Thu, 27 Apr 2017 00:50:13 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f90fe989159228e1a52c6ebcdd77f24bdfb29268a591ade68b275e1c07fe350c`  
		Last Modified: Thu, 27 Apr 2017 00:50:12 GMT  
		Size: 1.5 KB (1541 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e487eda6fd4071404dbbb812d604cf83235d5ff01edc290d60fff53141ca17fe`  
		Last Modified: Thu, 27 Apr 2017 00:50:12 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c46256fd6f8ec6158009c00a05377be73b3981094fcbf9d2f5940848d1b2b4b5`  
		Last Modified: Thu, 27 Apr 2017 00:50:12 GMT  
		Size: 572.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
