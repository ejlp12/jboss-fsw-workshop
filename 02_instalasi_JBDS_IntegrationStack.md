Untuk men-develop menggunakan FSW versi 6.0 kita membuatuhkan JBoss Developer Studio (JBDS) versi 7.1.x dengan JBoss Developer Studio Integration Stack (Switchyard Tooling)

Ada baiknya ada lihat juga dulu video instalasi JBDS dan Switchyard Tooling berikut:

[Episode 4 : Eclipse Tooling Introduction](https://vimeo.com/57879770)

Detail cara instalasi di dokumentasi dapat dilihat di link berikut:

[Chapter 7. Installing JBoss Developer Studio](https://access.redhat.com/documentation/en-US/Red_Hat_JBoss_Fuse_Service_Works/6.0/html/Getting_Started_Guide/chap-Installing_JBoss_Developer_Studio.html)


## Instal Apache Maven

Ekstrak file installer maven yang didownload `unzip ` 

Pindahkan ke folder tertentu misalnya `/home/redhat/maven`

```
export PATH=$PATH:/home/redhat/maven/bin
```

Test dengan perintah berikut:

```
mvn -version
```
Ouputnya seperti ini:

```
Apache Maven 3.3.3 (7994120775791599e205a5524ec3e0dfe41d4a06; 2015-04-22T18:57:37+07:00)
Maven home: /usr/local/Cellar/maven/3.3.3/libexec
Java version: 1.7.0_71, vendor: Oracle Corporation
Java home: /Library/Java/JavaVirtualMachines/jdk1.7.0_71.jdk/Contents/Home/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "10.10.3", arch: "x86_64", family: "mac"
```



