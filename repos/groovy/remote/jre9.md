## `groovy:jre9`

```console
$ docker pull groovy@sha256:73467fb0fe25e61308544fcf0ca2a94de9c841be18c71be2d8bf4b88fbf3fb48
```

-	Platforms:
	-	linux; amd64

### `groovy:jre9` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **259.4 MB (259437630 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f25c726a5ea6017e98dfe68f0e00a0567e320733ab75967f8cbb0b2b5418fd7b`
-	Default Command: `["groovysh"]`

```dockerfile
# Mon, 24 Apr 2017 19:23:43 GMT
ADD file:c473955c7b4205ed3e562fd42f0e8a0dc2b73d83a951d1302c5934bccd4595e1 in / 
# Mon, 24 Apr 2017 19:23:44 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 19:56:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:44:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:44:46 GMT
RUN echo 'deb http://deb.debian.org/debian experimental main' > /etc/apt/sources.list.d/experimental.list
# Tue, 25 Apr 2017 00:44:47 GMT
ENV LANG=C.UTF-8
# Tue, 25 Apr 2017 00:44:48 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 25 Apr 2017 00:44:49 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-9-openjdk-amd64
# Tue, 25 Apr 2017 00:44:49 GMT
ENV JAVA_VERSION=9~b161
# Tue, 25 Apr 2017 00:44:50 GMT
ENV JAVA_DEBIAN_VERSION=9~b161-1
# Wed, 26 Apr 2017 23:12:19 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y 		openjdk-9-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$JAVA_HOME" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$JAVA_HOME" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 27 Apr 2017 00:26:23 GMT
CMD ["groovysh"]
# Thu, 27 Apr 2017 00:26:24 GMT
ENV GROOVY_HOME=/opt/groovy
# Thu, 27 Apr 2017 00:26:25 GMT
ENV GROOVY_VERSION=2.4.10
# Thu, 27 Apr 2017 00:26:37 GMT
RUN set -o errexit -o nounset 	&& echo "Downloading Groovy" 	&& wget --no-verbose --output-document=groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Installing build dependencies" 	&& apt-get update 	&& apt-get update && apt-get install --yes --no-install-recommends 		dirmngr 		gnupg 	&& rm --recursive /var/lib/apt/lists/* 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"0x41321490758AAD6F" 		"0x825C06C827AF6B66" 		"0x6A65176A0FB1CD0B" 	; do 		for server in 			ha.pool.sks-keyservers.net 			hkp://p80.pool.sks-keyservers.net:80 			pgp.mit.edu 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 3 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget --no-verbose --output-document=groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm --recursive --force "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln --symbolic "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln --symbolic "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln --symbolic "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln --symbolic "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln --symbolic "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln --symbolic "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln --symbolic "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& echo $(apt-mark showauto) 	&& apt-get remove --yes --purge 		dirmngr 		gnupg 	&& apt-get autoremove --yes --purge 		&& echo "Adding groovy user and group" 	&& groupadd --system --gid 1000 groovy 	&& useradd --system --gid groovy --uid 1000 --shell /bin/bash --create-home groovy 	&& mkdir --parents /home/groovy/.groovy/grapes 	&& chown --recursive groovy:groovy /home/groovy 		&& echo "Applying workaround for https://github.com/docker-library/openjdk/issues/101" 	&& bash -c '([[ ! -d $JAVA_SECURITY_DIR ]] && ln -s $JAVA_HOME/lib $JAVA_HOME/conf) || (echo "Found java conf dir, package has been fixed, remove this hack"; exit -1)'
# Thu, 27 Apr 2017 00:26:38 GMT
USER [groovy]
# Thu, 27 Apr 2017 00:26:39 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Thu, 27 Apr 2017 00:26:40 GMT
WORKDIR /home/groovy
# Thu, 27 Apr 2017 00:26:42 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:a841bbfc2677931730fc87f2ae744411bafc92235b68ca88a21443c2a9adaa55`  
		Last Modified: Mon, 24 Apr 2017 19:35:43 GMT  
		Size: 45.2 MB (45249494 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d5c09827328edda71795dc28781e627950f1a5bbec385201080f5aed329daba`  
		Last Modified: Mon, 24 Apr 2017 22:23:11 GMT  
		Size: 21.4 MB (21397541 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2bbe4930e094ecb48add6ca6cd62e32393a18c4d7d9607f65d52674a9237e718`  
		Last Modified: Tue, 25 Apr 2017 00:59:44 GMT  
		Size: 633.9 KB (633905 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e31361d0a03141658f7b0f6846501453a527d2eabd9f6cc955e85856946e3703`  
		Last Modified: Tue, 25 Apr 2017 00:59:43 GMT  
		Size: 213.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb341f064078bd9d84e2bd5044e8e9d81692f08550615028bac9dcd331af0c95`  
		Last Modified: Tue, 25 Apr 2017 00:59:43 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28bac90ee8e16252c62689e16a80da0deed15609936be8ef30419dee22cedd12`  
		Last Modified: Wed, 26 Apr 2017 23:28:39 GMT  
		Size: 155.6 MB (155591557 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb25030b4ea263edae244d79906779c6eb9563ed390f16101a1953684287ebfb`  
		Last Modified: Thu, 27 Apr 2017 00:42:19 GMT  
		Size: 36.6 MB (36564543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:624cbc12c8020d5016a6bced0507f33b70fc2c287a540fa81606658102ae6a4a`  
		Last Modified: Thu, 27 Apr 2017 00:42:17 GMT  
		Size: 137.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
