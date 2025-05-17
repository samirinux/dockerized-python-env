FROM ubuntu:25.04

WORKDIR /usr/src/app

# Install dependencies for building Python
RUN apt-get update && apt-get install -y \
    wget \
    build-essential \
    libssl-dev \
    zlib1g-dev \
    libncurses5-dev \
    libncursesw5-dev \
    libreadline-dev \
    libsqlite3-dev \
    libgdbm-dev \
    libdb5.3-dev \
    libbz2-dev \
    libexpat1-dev \
    liblzma-dev \
    tk-dev \
    libffi-dev \
    git \
    curl

# Download and install Python 3.14 (pre-release or latest dev)
RUN wget https://www.python.org/ftp/python/3.14.0/Python-3.14.0a4.tgz && \
    tar -xzf Python-3.14.0a4.tgz && \
    cd Python-3.14.0a4 && \
    ./configure --enable-optimizations && \
    make -j$(nproc) && \
    make altinstall && \
    cd .. && \
    rm -rf Python-3.14.0a4 Python-3.14.0a4.tgz

# Use python3.14 and pip3.14
RUN ln -sf /usr/local/bin/python3.14 /usr/bin/python3 && \
    ln -sf /usr/local/bin/pip3.14 /usr/bin/pip3

RUN curl -LsSf https://astral.sh/uv/install.sh | env UV_INSTALL_DIR="/usr/local/bin" sh

COPY . .

RUN uv sync 

CMD ["bash"]
