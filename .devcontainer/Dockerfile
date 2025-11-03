FROM ubuntu:22.04

RUN apt-get update && \
    apt-get install -y openjdk-17-jdk wget unzip git cmake ninja-build curl build-essential && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir -p /opt/android-sdk && \
    cd /opt/android-sdk && \
    wget https://dl.google.com/android/repository/commandlinetools-linux-8512546_latest.zip -O tools.zip && \
    unzip tools.zip && \
    rm tools.zip

ENV ANDROID_SDK_ROOT=/opt/android-sdk
ENV PATH=$PATH:/opt/android-sdk/cmdline-tools/bin:/opt/android-sdk/platform-tools

RUN yes | sdkmanager --licenses
