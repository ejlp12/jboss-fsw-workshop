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

## Setting Maven Repository

Jika anda terkoneksi ke internet, anda bisa men-setup agar Maven menggunakan online repository. 
Caranya, anda buka file `~/.m2/setting.xml` dan edit sehingg memiliki elemen *profiles* seperti ini:

```xml
<profiles>
    <!-- Profile with online repositories required by Fuse Service Works -->
    <profile>
      <id>fsw-online-repos</id>
      <repositories>
        <repository>
          <id>jboss-ga-repository</id>
          <url>http://maven.repository.redhat.com/techpreview/all</url>
          <releases>
            <enabled>true</enabled>
          </releases>
          <snapshots>
            <enabled>false</enabled>
          </snapshots>
        </repository>
        <repository>
          <id>jboss-public-repository</id>
          <url>http://repository.jboss.org/nexus/content/repositories/public/</url>
          <releases>
            <enabled>true</enabled>
          </releases>
          <snapshots>
            <enabled>false</enabled>
          </snapshots>
        </repository>
      </repositories>
      <pluginRepositories>
        <pluginRepository>
          <id>jboss-ga-plugin-repository</id>
          <url>http://maven.repository.redhat.com/techpreview/all</url>
          <releases>
            <enabled>true</enabled>
          </releases>
          <snapshots>
            <enabled>false</enabled>
          </snapshots>
        </pluginRepository>
        <pluginRepository>
          <id>jboss-public-plugin-repository</id>
          <url>http://repository.jboss.org/nexus/content/repositories/public/</url>
          <releases>
            <enabled>true</enabled>
          </releases>
          <snapshots>
            <enabled>false</enabled>
          </snapshots>
        </pluginRepository>
      </pluginRepositories>
    </profile>    
  </profiles>

  <activeProfiles>
    <!-- Activation of the Fuse Service Works profile -->
    <activeProfile>fsw-online-repos</activeProfile>
  </activeProfiles>
```

Detail cara setup juga dijelaskan di dokumentasi:

[6.4. Configuring Maven to Use the Online Repositories](https://access.redhat.com/documentation/en-US/Red_Hat_JBoss_Fuse_Service_Works/6.0/html/Getting_Started_Guide/chap-Maven_Repositories.html#Configure_the_JBoss_EAP_Integration_Maven_Repository_Using_the_Maven_Settings)


