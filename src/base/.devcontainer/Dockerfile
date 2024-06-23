ARG VARIANT

FROM debian:${VARIANT}

RUN apt-get update && apt-get install -y \
    sudo \
    libssl-dev \
    lsb-release \
    musl-dev \
    make \
    git \
    qemu-kvm \
    ca-certificates \
    perl \
    curl \
    gzip \
    && rm -rf /var/lib/apt/lists/*

RUN groupadd -r kvm

# Install Rust
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- --default-toolchain stable -y
ENV PATH="/root/.cargo/bin:${PATH}"
ENV CARGO_HOME=/root/.cargo

WORKDIR /workspaces