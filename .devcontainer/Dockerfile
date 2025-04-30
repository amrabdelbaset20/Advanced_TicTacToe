FROM mcr.microsoft.com/devcontainers/cpp:ubuntu-22.04

RUN apt-get update && apt-get install -y \
    cmake \
    qt6-base-dev \
    libsqlite3-dev \
    ninja-build \
    && rm -rf /var/lib/apt/lists/*
