## `mongo:unstable-windowsservercore`

```console
$ docker pull mongo@sha256:f9d820e35fa02d9709c2c0a6debb5813c35c68949b794e4617a5ddd9cc532b97
```

-	Platforms:
	-	windows; amd64

### `mongo:unstable-windowsservercore` - windows; amd64

-	Docker Version: 1.12.2-cs2-ws-beta
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.3 GB (5295267441 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:59c06aee055c5f61e3c30eaac11477ed3035befc15f9de1b53659de152b68483`
-	Default Command: `["mongod"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Tue, 22 Nov 2016 23:24:24 GMT
RUN Apply image 10.0.14393.0
# Mon, 10 Apr 2017 22:00:56 GMT
RUN Install update 10.0.14393.1066
# Tue, 18 Apr 2017 17:08:48 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Tue, 18 Apr 2017 17:12:51 GMT
ENV MONGO_VERSION=3.5.6
# Tue, 18 Apr 2017 17:12:54 GMT
ENV MONGO_DOWNLOAD_URL=http://downloads.mongodb.org/win32/mongodb-win32-x86_64-2008plus-ssl-3.5.6-signed.msi
# Tue, 18 Apr 2017 17:12:58 GMT
ENV MONGO_DOWNLOAD_SHA256=c92b82a10d53f4801126c32e16b4beaa78b99d71d0a97769fd4eba359e0d32b6
# Tue, 18 Apr 2017 17:13:48 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Tue, 18 Apr 2017 17:13:55 GMT
VOLUME [C:\data\db C:\data\configdb]
# Tue, 18 Apr 2017 17:13:58 GMT
EXPOSE 27017/tcp
# Tue, 18 Apr 2017 17:14:01 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:6d4d50238ed13902c153bc3efc3a22f8a96bca4168ea03624d01da1063728dc2`  
		Size: 1.2 GB (1161902022 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:2869ce7d2a7c3a942c84de08ac9b045cb0a8deefa17949b571dffa5cd1cc28cd`  
		Last Modified: Tue, 18 Apr 2017 17:14:24 GMT  
		Size: 1.2 KB (1223 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:021add1049c41e71b4346a7f4edf3bda1d6ca5d4405666c78d687e00ba531709`  
		Last Modified: Tue, 18 Apr 2017 17:15:40 GMT  
		Size: 1.2 KB (1220 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc66fd10df3bd6050a0c0ddc1608d5ab31f295470aafada1215aa1f6034f3bfa`  
		Last Modified: Tue, 18 Apr 2017 17:15:40 GMT  
		Size: 1.2 KB (1225 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea6d49815abdcfab3f3271b88dfc4db7a9e31a4bfec4562b24ba00f700a6a381`  
		Last Modified: Tue, 18 Apr 2017 17:15:30 GMT  
		Size: 1.2 KB (1220 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a85ca6f7dc3f344ebe072ed90749e7cf282987ef0bf87ceb69ec7b9c23596ca5`  
		Last Modified: Tue, 18 Apr 2017 17:15:44 GMT  
		Size: 63.4 MB (63370955 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c59ef3570dffa4b6b852050a91e7554adbc18e53fb8384f616bdf9c8106c37cb`  
		Last Modified: Tue, 18 Apr 2017 17:15:31 GMT  
		Size: 1.2 KB (1228 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:29502ae9854fd9f094b68574acd4b0193df65f850f252474610aa34f27c5934e`  
		Last Modified: Tue, 18 Apr 2017 17:15:30 GMT  
		Size: 1.2 KB (1228 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d7e111540199b2ca87239d7c6f5f24cb8e8ba6e70a623215e9d116889b5b2eb`  
		Last Modified: Tue, 18 Apr 2017 17:15:31 GMT  
		Size: 1.2 KB (1220 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
