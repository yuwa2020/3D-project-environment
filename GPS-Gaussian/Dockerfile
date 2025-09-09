FROM nvcr.io/nvidia/cuda:11.8.0-devel-ubuntu22.04

# Install miniconda and git
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install ffmpeg libsm6 libxext6  -y \
    wget \
    git \
    build-essential \
    libegl1-mesa-dev \
    libnvidia-gl-535 \
    libgl1-mesa-glx \
    libglib2.0-0 \
    xvfb \ 
    && rm -rf /var/lib/apt/lists/*

RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O /tmp/miniconda.sh && \
    bash /tmp/miniconda.sh -b -p /opt/conda && \
    rm /tmp/miniconda.sh

ENV PATH="/opt/conda/bin:${PATH}"

# Activate conda base environment
RUN conda init bash && \
    echo "conda activate base" >> ~/.bashrc \
    source activate

