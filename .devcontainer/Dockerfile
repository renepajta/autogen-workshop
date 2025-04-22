# syntax=docker/dockerfile:1
ARG VARIANT=3.13-bullseye
FROM mcr.microsoft.com/devcontainers/python:${VARIANT}

# Use Bash for RUN commands so that 'source' works and uvenv setup can detect shell
SHELL ["/bin/bash", "-lc"]

# Non‑interactive apt + rustup/cargo paths + pip config
ENV DEBIAN_FRONTEND=noninteractive \
    RUSTUP_HOME=/usr/local/rustup \
    CARGO_HOME=/usr/local/cargo \
    PATH=/usr/local/cargo/bin:/usr/local/bin:$PATH \
    PIP_DISABLE_PIP_VERSION_CHECK=1 \
    PIP_NO_CACHE_DIR=1 \
    PIP_ROOT_USER_ACTION=ignore

# 1) Install system build‑deps, bootstrap Rust via rustup, then clean up
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      build-essential \
      cmake \
      curl \
      git \
      pkg-config \
      libdbus-1-dev \
      libglib2.0-dev && \
    rm -rf /var/lib/apt/lists/* 

# 2) Copy requirements & install Python deps + uvenv + IPython kernel
COPY requirements.txt /tmp/
RUN python3 -m pip install --upgrade pip && \
    pip install --no-cache-dir -r /tmp/requirements.txt && \
    pip install --no-cache-dir keyrings.alt dbus-python ipython ipykernel && \
    python3 -m ipykernel install --name python3 --user && \
    playwright install --with-deps chromium

# 3) Install the daily build of Azure Developer CLI
RUN curl -fsSL https://aka.ms/install-azd.sh | bash

# 4) Drop back to non‑root user
USER vscode
