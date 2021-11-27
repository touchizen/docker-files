# Open Java 11 image

This image is built to include latest version of Open JDK 11. It is based on [phusion/baseimage](https://registry.hub.docker.com/u/phusion/baseimage/) , so it inherts all goodies from it.

### Pulling image

A prebuilt container is available on Docker Hub, you can get it with following command

```sh
docker pull tuxxon/java11:0.1
```

### Usage

To test run it, run following command:

```sh
docker run --rm -P -t -i tuxxon/java11:0.1 /sbin/my_init -- bash -l
```
