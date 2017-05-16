FROM ubuntu:16.04

LABEL maintainer="DiffBlue Ltd."

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      g++ gcc make ccache bison flex libwww-perl patch git \
	  && rm -rf /var/lib/apt/lists/*

# Will be mounted to source during run
WORKDIR /cbmc
