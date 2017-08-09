FROM alpine:3.5

LABEL maintainer="DiffBlue Ltd."

RUN apk add --no-cache \
      # Compilation dependencies
      gcc \
      g++ \
      make \
      git \
      bison \
      flex \
      perl-libwww \
      # Test dependencies
      bash \
      # Optimisation
      ccache \
      parallel \
    && echo yes | cpan Thread::Pool::Simple

# Will be mounted to source during run
WORKDIR /cbmc
