FROM --platform=$BUILDPLATFORM mcr.microsoft.com/dotnet/nightly/sdk:latest

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