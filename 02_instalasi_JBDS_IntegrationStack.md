Untuk men-develop menggunakan FSW versi 6.0 kita membuatuhkan JBoss Developer Studio (JBDS) versi 7.1.x dengan JBoss Developer Studio Integration Stack (Switchyard Tooling)

Ada baiknya ada lihat juga dulu video instalasi JBDS dan Switchyard Tooling berikut:

* Video: [Episode 4 : Eclipse Tooling Introduction](https://vimeo.com/57879770)

Detail cara instalasi di dokumentasi dapat dilihat di link berikut:

[Chapter 7. Installing JBoss Developer Studio](https://access.redhat.com/documentation/en-US/Red_Hat_JBoss_Fuse_Service_Works/6.0/html/Getting_Started_Guide/chap-Installing_JBoss_Developer_Studio.html)

Setelah instalasi JBDS selesai, selanjutnya instal Eclipse plug-in "JBoss Developer Studio Integration Stack"

## Instalasi Integration Stack

Plugin Integration Stack dapat di-install dengan dua cara yaitu (1) instalasi secara online dan (2) instalasi secara offline.

(1) Instalasi online akan memudahkan untuk update plugin dikemudian hari.

- Pada *JBoss Central** view klik tab *SOftware/Update* dibagian bawah.
- Kemudian klik cekbox *JBoss Integration and SOA Development* lalu klik tombol *Install*

![image](https://cloud.githubusercontent.com/assets/3068071/10314259/1486cfb4-6c7e-11e5-8fde-51ca31fc9912.png)

(2) Instalasi offline bisa dilakukan tanpa koneksi internet. File installer plugin (berupa file ZIP) bisa didownload terlebih dahulu.

File plugin dapat didownload di [http://tools.jboss.org/downloads/overview.html](http://tools.jboss.org/downloads/overview.html)

## Instal Apache Maven

Sebelum kita memulai development menggunakan JBDS, kita perlu instal Apache Maven karena setiap project di JBDS untuk mendevelop komponen untuk integrasi di JBDS adalah sebuah Maven Project.


1. Download Apache Maven binary-file dari [https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi).
   Pilihlah file `.zip` atau `tar.gz`

2. Ekstrak file installer maven yang didownload tadi dengan perintah `unzip apache-maven-3.3.3-bin.zip` 

3. Pindahkan ke folder tertentu misalnya `/home/redhat/maven` dengan perintah 

   ```
   mv apache-maven-3.3.3-bin /home/redhat/maven
   ```

4. Setting *PATH* environment variable agar dapat mengeksekusi command `mvn` yang ada di direktori `/home/redhat/maven/bin`

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
5. Agar path diset secara 'permanen' (diset otomatis setiap anda login) masukan perintah `export` diatas ke dalam file `.bash_profile`

  ```
  echo "export PATH=\$PATH:/home/redhat/maven/bin" >> ~/.bash_profile
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


