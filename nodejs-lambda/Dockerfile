# arguments

ARG FUNCTION_DIR="/function"

# versions

FROM node:24-bookworm-slim AS base

FROM base AS builder

# labels
LABEL org.opencontainers.image.title="Node.js Lambda Base Image"
LABEL org.opencontainers.image.description="Node.js Lambda Base Image"
LABEL org.opencontainers.image.version="1.0.0"
LABEL org.opencontainers.image.authors="Eser Ozvataf <eser@acikyazilim.com>"
LABEL org.opencontainers.image.licenses="Apache-2.0"

# include FUNCTION_DIR
ARG FUNCTION_DIR

# install dependencies
RUN apt-get update && \
  apt-get -y install --no-install-recommends \
    automake \
    build-essential \
    cmake \
    g++ \
    libcurl4-openssl-dev \
    libtool \
    make \
    python3 \
    unzip

# set working directory
WORKDIR ${FUNCTION_DIR}

# install aws lambda interface
RUN npm install -g aws-lambda-ric

# set runtime interface client as default command for the container runtime
ENTRYPOINT ["/usr/local/bin/aws-lambda-ric"]

# pass the name of the function handler as an argument to the runtime
CMD ["index.handler"]
