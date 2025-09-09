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

# Run this code inside the docker
# source activate

# # Clone the repository with submodules in /github
# RUN mkdir -p /github
# WORKDIR /github
# RUN git clone --recursive https://github.com/graphdeco-inria/gaussian-splatting.git
# WORKDIR /github/gaussian-splatting

# # Create the conda environment using the environment.yml from the repo
# RUN conda env create -f environment.yml

# # Activate the environment
# RUN echo "source activate gaussian_splatting" > ~/.bashrc
# ENV PATH /opt/conda/envs/gaussian_splatting/bin:$PATH

# # Set the default command to run when starting the container
# CMD ["bash"]


# docker run --gpus '"device=1,2,4,5"' --shm-size=16g -it --rm -v /nfs/thundurus/data/md0:/nfs/thundurus/data/md0  -v /nfs/wattrel/data/md0:/nfs/wattrel/data/md0/ -v /nfs/gigantamax/home/data/:/nfs/gigantamax/home/data/ gps-gaussian

# Todo: run code to process dataset

# Follow GPS-Gaussin plus installation of PyTorch3D