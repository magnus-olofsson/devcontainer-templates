FROM --platform=$BUILDPLATFORM eclipse-temurin:25-jdk-noble

RUN apt-get update && apt-get install -y \
    curl \
    wget \
    unzip \
    git \
    jq \
    httpie \
    iputils-ping \
    netcat-openbsd \
    vim \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Maven
ARG MAVEN_VERSION=3.9.9
RUN wget https://archive.apache.org/dist/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.tar.gz -P /tmp \
    && tar xzf /tmp/apache-maven-${MAVEN_VERSION}-bin.tar.gz -C /opt \
    && ln -s /opt/apache-maven-${MAVEN_VERSION} /opt/maven \
    && rm /tmp/apache-maven-${MAVEN_VERSION}-bin.tar.gz

ENV MAVEN_HOME=/opt/maven
ENV PATH="${MAVEN_HOME}/bin:${PATH}"

# Camel JBang (via JBang)
RUN curl -Ls https://sh.jbang.dev | bash -s - app setup \
    && ~/.jbang/bin/jbang trust add https://github.com/apache/camel/ \
    && ~/.jbang/bin/jbang app install camel@apache/camel

ENV PATH="/root/.jbang/bin:${PATH}"