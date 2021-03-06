## `telegraf:alpine`

```console
$ docker pull telegraf@sha256:d74770e4e502870575cfc9da0b5ef67c6e7dafdb64300534fac65f79e5ed63d7
```

-	Platforms:
	-	linux; amd64

### `telegraf:alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **9.3 MB (9255308 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3280d4bdf3b62d058a6b47a2525766294ceb75ac77f6cb2bef7bb282fa086967`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:37 GMT
ADD file:730030a984f5f0c5dc9b15ab61da161082b5c0f6e112a9c921b42321140c3927 in / 
# Wed, 12 Apr 2017 18:58:25 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Wed, 12 Apr 2017 19:09:34 GMT
RUN apk add --no-cache iputils ca-certificates &&     update-ca-certificates
# Wed, 12 Apr 2017 19:09:49 GMT
ENV TELEGRAF_VERSION=1.2.1
# Wed, 12 Apr 2017 19:09:58 GMT
RUN apk add --no-cache --virtual .build-deps wget gnupg tar &&     gpg --keyserver hkp://ha.pool.sks-keyservers.net         --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5 &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Wed, 12 Apr 2017 19:09:59 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Wed, 12 Apr 2017 19:10:00 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Wed, 12 Apr 2017 19:10:00 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 12 Apr 2017 19:10:01 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:627beaf3eaaff1c0bc3311d60fb933c17ad04fe377e1043d9593646d8ae3bfe1`  
		Last Modified: Fri, 03 Mar 2017 20:34:41 GMT  
		Size: 1.9 MB (1905270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827570184fa82dc6defc05bcf5838dba590096d8add32bb847191bd7232cfcba`  
		Last Modified: Wed, 12 Apr 2017 19:02:02 GMT  
		Size: 155.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57fcd868acd0ceb3cebc641b09ed4bc217f4949f027ea4ec732071be73dd496c`  
		Last Modified: Wed, 12 Apr 2017 19:11:08 GMT  
		Size: 445.9 KB (445917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:956b685f03e1648653ee419643c83fb78b32e3e806c8f987f88fd2d07f6449aa`  
		Last Modified: Wed, 12 Apr 2017 19:12:57 GMT  
		Size: 6.9 MB (6903782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47934ed3a4dd3c9d7436b8e9a38deee1d4db4ae6abc1142714ca0e60a09ccf21`  
		Last Modified: Wed, 12 Apr 2017 19:12:55 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
