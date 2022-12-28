# get base ubutu image
FROM ubuntu:latest


# update repos and install required packages
RUN apt-get -qq update \
  && apt-get -qq install --no-install-recommends \
       build-essential \
       gcc \
       git \
       make \
       ca-certificates \
       libnuma-dev \
       python3-pip \
       python3-pyelftools \
       python3-setuptools \
       wget \
       xz-utils \
  && pip3 install \
       meson \
       ninja 
   
    
WORKDIR /root
RUN  git clone git://dpdk.org/dpdk 

# compile dpdk.
WORKDIR /root/dpdk
RUN meson build \
  && cd build \
  && ninja \
  && ninja install \
  && ldconfig


RUN make





