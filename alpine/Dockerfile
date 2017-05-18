FROM alpine:3.5

LABEL maintainer="DiffBlue Ltd."

RUN apk add --no-cache gcc g++ make ccache bison flex perl-libwww bash git

# Will be mounted to source during run
WORKDIR /cbmc
