FROM mcr.microsoft.com/devcontainers/cpp:ubuntu-22.04

# Install system dependencies
RUN apt-get update && \
    apt-get install -y \
    cmake \
    build-essential \
    qt6-base-dev \
    qt6-tools-dev \
    libsqlite3-dev \
    ninja-build \
    gdb \
    lcov \
    && rm -rf /var/lib/apt/lists/*

# Install latest CMake
RUN wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | gpg --dearmor - | tee /etc/apt/trusted.gpg.d/kitware.gpg >/dev/null && \
    apt-add-repository 'deb https://apt.kitware.com/ubuntu/ jammy main' && \
    apt-get update && \
    apt-get install -y cmake cmake-curses-gui ninja-build

# Install Google Test
WORKDIR /usr/src/googletest
RUN git clone https://github.com/google/googletest.git && \
    cmake -B build -S googletest -GNinja && \
    cmake --build build && \
    cmake --install build
