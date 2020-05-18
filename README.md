# basic-illumination
ImageJ BaSiC shading correction for use with Ashlar

Reference:     
Peng, T., Thorn, K., Schroeder, T. et al. A BaSiC tool for background and shading correction of optical microscopy images. Nat Commun 8, 14836 (2017). [https://doi.org/10.1038/ncomms14836](https://doi.org/10.1038/ncomms14836)

## Running as a Docker container

Create a container:
```
docker run -it -v /path/to/data:/data labsyspharm/basic-illumination bash
```
where `/path/to/data` is the data directory on your local machine. Your data will be mapped to `/data` inside the container.

Once inside the container, do `ls /data` to ensure your data is there, followed by
```
ImageJ-linux64 --ij2 --headless --run imagej_basic_ashlar.py \
  "filename='/data/input.ome.tiff',output_dir='/data/',experiment_name='my_experiment'"
```
for each `input.ome.tiff` in your data directory.
