# Builder
FROM node:lts-slim AS builder
RUN node --version

# Update deps
RUN apt-get update

# Get Ubuntu packages
RUN apt-get install -y build-essential curl git python3 pkg-config ca-certificates libssl-dev
RUN update-ca-certificates

# Install rust
RUN curl https://sh.rustup.rs -sSf | bash -s -- -y
ENV PATH="/root/.cargo/bin:${PATH}"
RUN cargo --help

WORKDIR /subql
RUN git clone https://github.com/neo-sun/demo-1.git .
RUN cargo build --release
