1. Download file `jboss-fsw-installer-6.0.0.GA-redhat-4.jar`

   Sebelum memulai instalasi baca dulu kebutuhan yang diperlukan untuk instalasi [Red Hat JBoss Fuse Service Works Supported Configurations](https://access.redhat.com/articles/626513), perhatikan versi JDK dan sistem operasi yang disupport.
   
   Jika anda menggunakan Mac OS-X, jangan khawatir FSW tetap bisa diinstal dan dijalankan, tetapi tidak disupport oleh Red Hat.
   
   > [X] Jangan menggunakan JDK/JRE 1.8 untuk installasi

2. Install dengan mode GUI (interaktif), buka console atau terminal lalu jalankan perintah berikut:

```
java -jar jboss-fsw-installer-6.0.0.GA-redhat-4.jar
```

atau install dengan mode text (interactif) dengan opsi `-console`

```
java -jar jboss-fsw-installer-6.0.0.GA-redhat-4.jar -console
```

> Anda bisa install sumsi saya, anda menginstall di direktori `/Servers/FSW_6`

3. Jalankan FSW

```
ce /Servers/FSW_6/jboss-eap-6.1/bin
./standalone
```

Tunggu sampai muncul tulisan berikut di terminal window anda:

```
04:55:37,001 INFO  [org.jboss.as] (Controller Boot Thread) JBAS015961: Http management interface listening on http://127.0.0.1:9990/management
04:55:37,002 INFO  [org.jboss.as] (Controller Boot Thread) JBAS015951: Admin console listening on http://127.0.0.1:9990
04:55:37,002 INFO  [org.jboss.as] (Controller Boot Thread) JBAS015874: JBoss Red Hat JBoss Fuse Service Works 6.0.0.GA-redhat-2 (AS 7.2.1.Final-redhat-10) started in 41617ms - Started 1093 of 1203 services (104 services are passive or on-demand)
```

4. 
