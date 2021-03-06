## `websphere-liberty:microProfile`

```console
$ docker pull websphere-liberty@sha256:31678d07e4563978082f06fe2972ce46b562d62eff070a9cba46c8cd05e5d89e
```

-	Platforms:
	-	linux; amd64

### `websphere-liberty:microProfile` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **197.3 MB (197343558 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:45ffe0b55bc7a161034b38532249efe9a57dd01d5d996f3ddf8d5e731c399916`
-	Default Command: `["\/opt\/ibm\/docker\/docker-server","run","defaultServer"]`

```dockerfile
# Mon, 24 Apr 2017 22:56:51 GMT
ADD file:141408db9037263a47322d1d78006be6a93927ac912bf14cd85100aa91da0421 in / 
# Mon, 24 Apr 2017 22:57:05 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Mon, 24 Apr 2017 22:57:06 GMT
RUN rm -rf /var/lib/apt/lists/*
# Mon, 24 Apr 2017 22:57:08 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Mon, 24 Apr 2017 22:57:09 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Mon, 24 Apr 2017 22:57:10 GMT
CMD ["/bin/bash"]
# Tue, 25 Apr 2017 00:05:46 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Tue, 25 Apr 2017 00:05:59 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:06:00 GMT
ENV JAVA_VERSION=1.8.0_sr4fp2
# Tue, 25 Apr 2017 00:06:36 GMT
RUN ESUM="9f319ba22cda861a7ccf39ec1e9877a73dc2f1a2a77822f441ffb5b1d9867f16"     && BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/"     && YML_FILE="jre/linux/x86_64/index.yml"     && wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml $BASE_URL/$YML_FILE     && JAVA_URL=$(cat /tmp/index.yml | sed -n '/'$JAVA_VERSION'/{n;p}' | sed -n 's/\s*uri:\s//p' | tr -d '\r')     && wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin $JAVA_URL     && echo "$ESUM  /tmp/ibm-java.bin" | sha256sum -c -     && echo "INSTALLER_UI=silent" > /tmp/response.properties     && echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties     && echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties     && mkdir -p /opt/ibm     && chmod +x /tmp/ibm-java.bin     && /tmp/ibm-java.bin -i silent -f /tmp/response.properties     && rm -f /tmp/response.properties     && rm -f /tmp/index.yml     && rm -f /tmp/ibm-java.bin
# Tue, 25 Apr 2017 00:06:37 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 25 Apr 2017 05:59:33 GMT
MAINTAINER David Currie <david_currie@uk.ibm.com> (@davidcurrie)
# Tue, 25 Apr 2017 05:59:41 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 05:59:42 GMT
ENV LIBERTY_VERSION=17.0.0_01
# Tue, 25 Apr 2017 05:59:42 GMT
ARG LIBERTY_URL
# Tue, 25 Apr 2017 05:59:43 GMT
ARG DOWNLOAD_OPTIONS=
# Tue, 25 Apr 2017 05:59:47 GMT
# ARGS: DOWNLOAD_OPTIONS=
RUN LIBERTY_URL=${LIBERTY_URL:-$(wget -q -O - https://public.dhe.ibm.com/ibmdl/export/pub/software/websphere/wasdev/downloads/wlp/index.yml  | grep $LIBERTY_VERSION -A 6 | sed -n 's/\s*kernel:\s//p' | tr -d '\r' )}      && wget $DOWNLOAD_OPTIONS $LIBERTY_URL -U UA-IBM-WebSphere-Liberty-Docker -O /tmp/wlp.zip     && unzip -q /tmp/wlp.zip -d /opt/ibm     && rm /tmp/wlp.zip
# Tue, 25 Apr 2017 05:59:47 GMT
ENV PATH=/opt/ibm/wlp/bin:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 25 Apr 2017 05:59:48 GMT
ENV LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ibm/wlp/output
# Tue, 25 Apr 2017 05:59:49 GMT
# ARGS: DOWNLOAD_OPTIONS=
RUN mkdir /logs     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ibm/wlp/usr/servers/defaultServer /config
# Tue, 25 Apr 2017 05:59:51 GMT
# ARGS: DOWNLOAD_OPTIONS=
RUN /opt/ibm/wlp/bin/server create     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea
# Tue, 25 Apr 2017 05:59:52 GMT
COPY file:53b1bf224098174489129fdc8fec40f8eb4b3d0bf09e3028796a285d9a3457f1 in /opt/ibm/docker/ 
# Tue, 25 Apr 2017 05:59:53 GMT
EXPOSE 9080/tcp 9443/tcp
# Tue, 25 Apr 2017 05:59:53 GMT
CMD ["/opt/ibm/docker/docker-server" "run" "defaultServer"]
# Tue, 25 Apr 2017 06:00:10 GMT
ARG REPOSITORIES_PROPERTIES=
# Tue, 25 Apr 2017 06:00:11 GMT
COPY file:85a1543c7ae96e8459a3ecdbc26e3041e476ac27a7895e24ea438f07dd0552f7 in /config/ 
# Wed, 26 Apr 2017 15:46:25 GMT
# ARGS: REPOSITORIES_PROPERTIES=
RUN if [ ! -z $REPOSITORIES_PROPERTIES ]; then mkdir /opt/ibm/wlp/etc/     && echo $REPOSITORIES_PROPERTIES > /opt/ibm/wlp/etc/repositories.properties; fi     && installUtility install --acceptLicense       appSecurity-2.0 localConnector-1.0 ssl-1.0 microProfile-1.0 transportSecurity-1.0     && if [ ! -z $REPOSITORIES_PROPERTIES ]; then rm /opt/ibm/wlp/etc/repositories.properties; fi     && rm -rf /output/workarea /output/logs
```

-	Layers:
	-	`sha256:aafe6b5e13de557451e1781fe7276620275625f970015cbd10036ab7d8ae27c0`  
		Last Modified: Thu, 20 Apr 2017 10:34:07 GMT  
		Size: 46.8 MB (46792902 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a2b43a726608d3835aa027bbe181624789130c212eb191baa481f1d788a0676`  
		Last Modified: Mon, 24 Apr 2017 23:02:15 GMT  
		Size: 815.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18bdd1e546d21240bd4c3e4e29032a38f18102d780a78686508d40fe01c60158`  
		Last Modified: Mon, 24 Apr 2017 23:02:16 GMT  
		Size: 514.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8198342c3e05101bb56b0a585dc34e39346ece39ee5d39287cda24b1fb445fed`  
		Last Modified: Mon, 24 Apr 2017 23:02:15 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f56970a44fd409805e3872cac236d29f5eed1a45e189bb765bcd2163c915f384`  
		Last Modified: Mon, 24 Apr 2017 23:02:15 GMT  
		Size: 161.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d56020343345d1c18959a22ff99361fb266de10932136b50fe1f6efccc68d675`  
		Last Modified: Tue, 25 Apr 2017 18:15:21 GMT  
		Size: 3.1 MB (3070209 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d2382b3247372a77ea8061d9d3d574771b6f75a04acf48ad31d81e43a4dab66`  
		Last Modified: Tue, 25 Apr 2017 18:15:34 GMT  
		Size: 110.9 MB (110850713 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b3450c8fb38f02f65560ac97d897fd345966fbb73d6af7556051f9d507140e4`  
		Last Modified: Tue, 25 Apr 2017 22:25:33 GMT  
		Size: 269.2 KB (269237 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df67195806cd01ff7a9423b2431906cbb4082ba52e75c4015715f79eb39556fa`  
		Last Modified: Tue, 25 Apr 2017 22:25:34 GMT  
		Size: 11.7 MB (11749675 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7193b08fe54d329890c060a0d125960cdde1aa540eb1de288251c95505c9d830`  
		Last Modified: Tue, 25 Apr 2017 22:25:36 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05bfcfccd06294beee338cbb12b799b6cc13e100dbd3c93fa49f0e426e96dbfd`  
		Last Modified: Tue, 25 Apr 2017 22:25:33 GMT  
		Size: 578.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1382e909e95cea412044d1f6af809d949bcf1559902c1cd4ed73f70010e70e98`  
		Last Modified: Tue, 25 Apr 2017 22:25:33 GMT  
		Size: 464.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:be9d392d1911025a3c8a6ce1e1b962d6b3335ad40f096b04a000f08240e89382`  
		Last Modified: Tue, 25 Apr 2017 22:25:59 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb4164952589c554112734dfa46cef1223f14b7b4cc05516d2832dd85376673c`  
		Last Modified: Wed, 26 Apr 2017 15:49:30 GMT  
		Size: 24.6 MB (24606730 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
