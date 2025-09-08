```
docker run --gpus '"device=1,2,4,5,7"' --shm-size=16g -it --rm -v /nfs/thundurus/data/md0:/nfs/thundurus/data/md0  -v /nfs/wattrel/data/md0:/nfs/wattrel/data/md0/ -v /nfs/gigantamax/home/data/datasets/ThumanMV/THumanMV:/nfs/gigantamax/home/data/datasets/ThumanMV/THumanMV gps-gaussian
```

```
cd /nfs/wattrel/data/md0/yuhirata_files/data/GPS_plus
```

```
conda env create --file enviroment.yml
```

```
conda activate gps_plus
```

Follow the github instructions on GPS_plus

(
```
git clone https://github.com/graphdeco-inria/gaussian-splatting --recursive
cd gaussian-splatting/
pip install -e submodules/diff-gaussian-rasterization
cd ..
```

)



