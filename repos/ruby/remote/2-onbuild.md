## `ruby:2-onbuild`

```console
$ docker pull ruby@sha256:e55d6e7617dc8e5b83279f6673547b8d7484b4a794e7405e1371de289a46787f
```

-	Platforms:
	-	linux; amd64

### `ruby:2-onbuild` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **268.7 MB (268718349 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8593e7a5dd3b179c6b7825049ab67f0cc87d05bb117bfc4b9214ef123db018f9`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 19:54:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 24 Apr 2017 19:55:32 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 24 Apr 2017 22:15:00 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 14:37:17 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 25 Apr 2017 14:37:18 GMT
ENV RUBY_MAJOR=2.4
# Tue, 25 Apr 2017 14:37:19 GMT
ENV RUBY_VERSION=2.4.1
# Tue, 25 Apr 2017 14:37:36 GMT
ENV RUBY_DOWNLOAD_SHA256=4fc8a9992de3e90191de369270ea4b6c1b171b7941743614cc50822ddc1fe654
# Tue, 25 Apr 2017 14:37:36 GMT
ENV RUBYGEMS_VERSION=2.6.11
# Tue, 25 Apr 2017 14:41:01 GMT
RUN set -ex 		&& buildDeps=' 		bison 		libgdbm-dev 		ruby 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& ./configure --disable-install-doc --enable-shared 	&& make -j"$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION"
# Tue, 25 Apr 2017 14:41:17 GMT
ENV BUNDLER_VERSION=1.14.6
# Tue, 25 Apr 2017 14:41:19 GMT
RUN gem install bundler --version "$BUNDLER_VERSION"
# Tue, 25 Apr 2017 14:41:20 GMT
ENV GEM_HOME=/usr/local/bundle
# Tue, 25 Apr 2017 14:41:37 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Tue, 25 Apr 2017 14:41:37 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 25 Apr 2017 14:41:39 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Tue, 25 Apr 2017 14:41:39 GMT
CMD ["irb"]
# Tue, 25 Apr 2017 14:42:30 GMT
RUN bundle config --global frozen 1
# Tue, 25 Apr 2017 14:42:32 GMT
RUN mkdir -p /usr/src/app
# Tue, 25 Apr 2017 14:42:33 GMT
WORKDIR /usr/src/app
# Tue, 25 Apr 2017 14:42:49 GMT
ONBUILD COPY Gemfile /usr/src/app/
# Tue, 25 Apr 2017 14:42:50 GMT
ONBUILD COPY Gemfile.lock /usr/src/app/
# Tue, 25 Apr 2017 14:42:50 GMT
ONBUILD RUN bundle install
# Tue, 25 Apr 2017 14:42:51 GMT
ONBUILD COPY . /usr/src/app
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
	-	`sha256:85334a7c200103c122f3cbf56460f28fe688abc52655dc714afa939e49848ba8`  
		Last Modified: Mon, 24 Apr 2017 22:20:21 GMT  
		Size: 43.2 MB (43231315 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c546d9d6a84ca2a1b7459a47978abe757bf67096d9dd704a9a5a0a786d2d325`  
		Last Modified: Mon, 24 Apr 2017 22:21:26 GMT  
		Size: 131.8 MB (131793725 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dd2ea17fcd18aebba250c8b5681bb0cbc4b14b7521eada0b7582d2a301dfdd47`  
		Last Modified: Tue, 25 Apr 2017 21:36:34 GMT  
		Size: 201.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:234e7744cd9b95842f4888f19ec939012f80e7d18d1dcda8fb4b206709ec98e0`  
		Last Modified: Tue, 25 Apr 2017 21:44:03 GMT  
		Size: 21.2 MB (21236723 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dcbfbb4bf16fc54b20fad674728e4a1f248627c06f410bbe2a5b97bcf9005b0d`  
		Last Modified: Tue, 25 Apr 2017 21:43:55 GMT  
		Size: 639.4 KB (639413 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:97488e0bf2cc95ae51ee3ec023a13f2a70374e8d9b2d9cb7b0dc32f1d7b97f59`  
		Last Modified: Tue, 25 Apr 2017 21:43:55 GMT  
		Size: 159.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:654cb1772487c729f5a945bf276e93ecf738a9111ed3039b0be5635161e9d8ee`  
		Last Modified: Tue, 25 Apr 2017 21:45:23 GMT  
		Size: 186.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46d21db074a44beba70af3ae607312f4c868443320e3bfb85d00e9a8f1589beb`  
		Last Modified: Tue, 25 Apr 2017 21:45:23 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
