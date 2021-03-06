## `postgres:latest`

```console
$ docker pull postgres@sha256:fd6c0e2a9d053bebb294bb13765b3e01be7817bf77b01d58c2377ff27a4a46dc
```

-	Platforms:
	-	linux; amd64

### `postgres:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **104.3 MB (104254425 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:390220867755ef4d1351705130960605d14a44518149e89c674189eefcb09306`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Tue, 25 Apr 2017 04:07:06 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 25 Apr 2017 04:07:07 GMT
ENV GOSU_VERSION=1.7
# Tue, 25 Apr 2017 04:07:25 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 25 Apr 2017 04:07:35 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 25 Apr 2017 04:07:44 GMT
ENV LANG=en_US.utf8
# Tue, 25 Apr 2017 04:07:46 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 25 Apr 2017 04:07:49 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 25 Apr 2017 04:08:03 GMT
ENV PG_MAJOR=9.6
# Tue, 25 Apr 2017 04:08:04 GMT
ENV PG_VERSION=9.6.2-1.pgdg80+1
# Tue, 25 Apr 2017 04:08:06 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Tue, 25 Apr 2017 04:08:40 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 04:08:52 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Tue, 25 Apr 2017 04:08:53 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Tue, 25 Apr 2017 04:08:54 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 25 Apr 2017 04:08:55 GMT
ENV PGDATA=/var/lib/postgresql/data
# Tue, 25 Apr 2017 04:09:12 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Tue, 25 Apr 2017 04:09:12 GMT
VOLUME [/var/lib/postgresql/data]
# Tue, 25 Apr 2017 04:09:13 GMT
COPY file:e7038391d43a570dfa6f5c9fd1327eab0e66c902a643f547a29a71cbc660b950 in /usr/local/bin/ 
# Tue, 25 Apr 2017 04:09:31 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 25 Apr 2017 04:09:31 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 25 Apr 2017 04:09:32 GMT
EXPOSE 5432/tcp
# Tue, 25 Apr 2017 04:09:48 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c784d04dcb093d973443d53da4caa360237c8402351f61ec29a7a4d94e74223`  
		Last Modified: Tue, 25 Apr 2017 20:57:35 GMT  
		Size: 2.1 KB (2058 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d99dddf7e66202708c779d83f4155703ded0b0a34273d20ff88c587ce18619fb`  
		Last Modified: Tue, 25 Apr 2017 20:57:35 GMT  
		Size: 1.3 MB (1308214 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5bff71e3ce6a34b054c75497bf6d379053ee0bf2348b1b3b7941f0901fbcb38`  
		Last Modified: Tue, 25 Apr 2017 20:57:36 GMT  
		Size: 7.1 MB (7117661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb3e0a8654888a301af8ce50e4c63c7e3762dca8a4cd1b165ec0b80f6dcf6c03`  
		Last Modified: Tue, 25 Apr 2017 20:57:32 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:31295d654cd5ed8581f46fbe2b7fb364302bcb01a58b887b934a4686f31e1cd9`  
		Last Modified: Tue, 25 Apr 2017 20:57:34 GMT  
		Size: 4.5 KB (4489 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc930a4e09f51d3334809e42a7afeedc0b284f1e440030869e116cf33dba86cb`  
		Last Modified: Tue, 25 Apr 2017 21:01:21 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8650cce8ef01c166a4e56b69db0a54c8795a5aa5b2e791f3c33c83906bc64a28`  
		Last Modified: Tue, 25 Apr 2017 21:01:33 GMT  
		Size: 43.3 MB (43262082 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61949acd8e523ea00b73838652d948c36bd11ff920221e59acfbc2dbc738af50`  
		Last Modified: Tue, 25 Apr 2017 21:01:18 GMT  
		Size: 7.1 KB (7096 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:527a203588c0f7065060fab3f9de27f3e79b8ad61d3df599423e4b4108e61092`  
		Last Modified: Tue, 25 Apr 2017 21:01:18 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26dec14ac775661620d3ee9c5e72a10b10f95741d70b225962f74a5f40cd6ed6`  
		Last Modified: Tue, 25 Apr 2017 21:01:18 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0efc0ed5a9e5634caf56c65f24a136cf6ae7a663f10181e84ae5531a8b538700`  
		Last Modified: Tue, 25 Apr 2017 21:01:19 GMT  
		Size: 1.8 KB (1795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40cd26695b38fcd575c4ae6e8369b9103d65c0b1a781dadb610aebeaaf2141d7`  
		Last Modified: Tue, 25 Apr 2017 21:01:18 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
