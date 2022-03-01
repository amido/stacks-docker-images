# This image builds on the base image and installs Java SDK
# for building applications

FROM azul/zulu-openjdk-debian:11

ARG MAVEN_VERSION=3.8.4

# Install Maven
RUN curl "https://dlcdn.apache.org/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.zip" -o /tmp/maven.zip && \
    unzip /tmp/maven.zip -d /usr/local && \
    rm /tmp/maven.zip 


RUN apt-get update && apt-get install -y gnupg gnupg-agent

# Update the path so maven can be found
ENV PATH="/usr/local/apache-maven-${MAVEN_VERSION}/bin:$PATH"
