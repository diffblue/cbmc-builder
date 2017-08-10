FROM ubuntu:16.04

LABEL maintainer="DiffBlue Ltd."

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      # Compilation dependencies
      gcc \
      g++ \
      make \
      patch \
      git \
      bison \
      flex \
      libwww-perl \
      # Optimisation
      ccache \
      parallel \
      libthread-pool-simple-perl \
	  && rm -rf /var/lib/apt/lists/*

# Will be mounted to source during run
WORKDIR /cbmc
