FROM docker.io/library/debian:experimental
ARG cmake_version=3.16.2 
  
RUN apt-get update && apt-get install -y curl \
  && curl -LsS https://github.com/Kitware/CMake/releases/download/v${cmake_version}/cmake-${cmake_version}-Linux-x86_64.tar.gz \
  | tar  -C /opt -xzf - \
  && apt-get dist-upgrade -y \
  && apt-get install -y ninja-build \
  && apt-get install -y -t experimental g++ \
  && apt-get -y remove --purge curl \
  && apt-get -y autoremove \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
 
ENV PATH /opt/cmake-${cmake_version}-Linux-x86_64/bin:$PATH
