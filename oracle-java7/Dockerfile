#
# Oracle Java 7 Dockerfile
#
# https://github.com/jpizarrom/armv7hf-java-dockerhub
# https://github.com/jpizarrom/armv7hf-java-dockerhub/tree/master/oracle-java7
#

# Pull base image.
FROM jpizarrom/armv7hf-debian-qemu:20170316

RUN [ "cross-build-start" ]

# Install Java.
RUN \
  echo deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main | tee /etc/apt/sources.list.d/webupd8team-java.list  && \
  apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EEA14886 && \
  echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  apt-get update && \
  apt-get install -y oracle-java7-installer && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/oracle-jdk7-installer

# Define working directory.
WORKDIR /data

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-7-oracle

# Define default command.
CMD ["bash"]

RUN [ "cross-build-end" ]
