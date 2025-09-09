```
docker run --gpus '"device=1,2,4,5,7"' --shm-size=16g -it --rm -v /nfs/thundurus/data/md0:/nfs/thundurus/data/md0  -v /nfs/wattrel/data/md0:/nfs/wattrel/data/md0/ -v /nfs/gigantamax/home/data/datasets/ThumanMV/THumanMV:/nfs/gigantamax/home/data/datasets/ThumanMV/THumanMV gps-gaussian
```

```
cd /nfs/wattrel/data/md0/yuhirata_files/data/GPS-Gaussian
```

```
conda env create --file environment.yml
conda activate gps_gaussian
```

```
git clone https://github.com/graphdeco-inria/gaussian-splatting --recursive
cd gaussian-splatting/
pip install -e submodules/diff-gaussian-rasterization
cd ..
```

```
git clone https://github.com/princeton-vl/RAFT-Stereo.git
cd RAFT-Stereo/sampler && python setup.py install && cd ../..
```

```
If compiled this CUDA implementation, set corr_implementation='reg_cuda' in config/stereo_human_config.py else corr_implementation='reg'.
```

https://github.com/aipixel/GPS-Gaussian/issues/71


Add this to ``gaussian_renderer/__init__.py``

```
antialiasing=True
```

Change this code (``line55``)
```
rendered_image, _, _ = rasterizer(
```