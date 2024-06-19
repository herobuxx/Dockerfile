FROM ubuntu:22.04
LABEL maintainer "HeroBuxx <herobuxx@gmail.com>"

ARG LC_ALL=C.UTF-8
ARG DEBIAN_FRONTEND=noninteractive 

# Install dependencies
RUN apt-get update -qqy && \
    apt-get install --no-install-recommends -y \
        autoconf \
        automake \
        autopoint \
        bc \
        binutils-dev \
        bison \
        build-essential \
        ca-certificates \
        ccache \
        clang \
        cmake \
        curl \
        dos2unix \
        expat \
        file \
        flex \
        gcc \
        gcc-10 \
        gcc-multilib \
        g++ \
        g++-10 \
        g++-multilib \
        gawk \
        gperf \
        gettext \
        gh \
        git \
        git-lfs \
        gnupg \
        help2man \
        hub \
        libcap-dev \
        libelf-dev \
        libexpat1-dev \
        libgmp-dev \
        liblz4-dev \
        liblz4-tool \
        liblzma-dev \
        libmpc-dev \
        libmpfr-dev \
        libncurses5-dev \
        libssl-dev \
        libtool \
        libz-dev \
        libzstd-dev \
        llvm \
        lld \
        lz4 \
        lzma \
        make \
        mercurial \
        ncurses-dev \
        ninja-build \
        patch \
        patchelf \
        pkg-config \
        python-all-dev \
        python3-dev \
        rclone \
        software-properties-common \
        ssh \
        subversion \
        sudo \
        texinfo \
        tzdata \
        txt2man \
        u-boot-tools \
        wget \
        xxd \
        xz-utils \
        zlib1g-dev \
        zstd \
        --fix-broken --fix-missing && \
    apt-get autoremove -qqy && \
    apt-get autoclean -qqy && \
    rm -rf /var/lib/apt/lists/*

# Add LLVM repository
RUN ubuntu_codename=$(lsb_release -c | cut -f2) && \
    wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key | apt-key add - && \
    add-apt-repository "deb http://apt.llvm.org/$ubuntu_codename/ llvm-toolchain-$ubuntu_codename main"

# Set environment variables
ENV USE_CCACHE=1

CMD ["/bin/bash"]
