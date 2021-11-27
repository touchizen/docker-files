# Tomcat 8 on Java 11

This image includes Tomcat 8 installation and deployment. It is based on [tuxxon/java11](https://registry.hub.docker.com/u/tuxxon/java11/) , check there what else is installed on it.

Tomcat runs as [runit](http://smarden.org/runit/) service. It is installed in /opt/tomcat dir, and includes Tomcat Manager for deployment of webapps.

To access Tomcat Manager:

 * Username: admin
 * Password: can be set when running docker container by passing TOMCAT_PASS env. veriable. Otherwise random password is generated on startup.

Password can be seen using command:

```sh
docker logs <container_id>
```

In log entry similar to this will appear:

```sh
========================================================================
You can now configure to this Tomcat server using:

    admin:6dD6x4f4IVKT

========================================================================
```

### Pulling image

A prebuilt container is available on Docker Hub, you can get it with following command

```sh
docker pull tuxxon/tomcat8-java11:0.1
```

### Usage

To test run it, run following command:

```sh
docker run --rm -P -t -i tuxxon/tomcat8-java11 /sbin/my_init -- bash -l
```

To run it as daemon, you can use command similar to this one:

```sh
docker run -d -p 49154:8080 --name app_name -e "JAVA_OPTS=-Dsome.property=value -Xmx1024m" -e "TOMCAT_PASS=somePass" tuxxon/tomcat8-java11:0.1
```


