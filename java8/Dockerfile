FROM phusion/baseimage:master

MAINTAINER Gordon Ahn <gordon.ahn@touchizen.com>

# Regenerate SSH host keys. baseimage-docker does not contain any, so you
# have to do that yourself. You may also comment out this instruction; the
# init system will auto-generate one during boot.
# RUN /etc/my_init.d/00_regen_ssh_host_keys.sh

# make sure the package repository is up to date and update ubuntu
RUN \
  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  apt-get update && \
  apt-get -y upgrade && \
  locale-gen en_US.UTF-8


# Install Oracle Java 8, telnet, wget
RUN \
   apt-get update && \
   apt-get install -y openjdk-8-jdk telnet wget && \
   rm -rf /var/lib/apt/lists/*

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

# Set correct environment variables.
ENV HOME /root



