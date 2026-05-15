FROM --platform=$BUILDPLATFORM python:3.13-slim

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

# Uppgradera pip
RUN pip install --upgrade pip