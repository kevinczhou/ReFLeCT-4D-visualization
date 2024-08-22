# ReFLeCT - 4D visualization
<ins>R</ins>eflective <ins>F</ins>ourier <ins>L</ins>ight field <ins>C</ins>omputed <ins>T</ins>omography (ReFLeCT) is a new high-throughput computational imaging technique that records dense 4D reconstructions (3D volumes over time). Its high frame rate (120 volumes per sec (vps)) and large volume of view (tens of cubic mm) enables simultaneous 4D imaging of multiple mm-size freely moving organisms (e.g., zebrafish and *Drosophila* larvae). This repository provides simple python code to visualize such 4D reconstructions interactively using [napari](https://napari.org/stable/index.html).

## 4D datasets
Two 4D ReFLeCT reconstructions can be downloaded from:
- [*Drosophila* larva expressing GFP (120 vps for 10 sec)](https://drive.google.com/drive/folders/1YpQqysDW4TS0CiIKmMzx7e0H4ssofgLc) (7.9 GB compressed, 103 GB decompressed)
- [Two zebrafish larva expressing GFP (120 vps for 10 sec)](https://drive.google.com/drive/folders/1S9nqzb7KIA6MP2e7uCAJf2lOw9lugmkU) (11.8 GB compressed, 154 GB decompressed)

Each 4D reconstruction consists of a sequence of `hdf5` files, each containing a compressed two-channel 3D volume at one time point. These 4D reconstructions are somewhat large, so feel free to download a subset of the time points.

## Setting up your python environment
We recommend following the [installation instructions on the napari site](https://napari.org/stable/tutorials/fundamentals/installation.html) and then installing a few additional required libraries (i.e., h5py, tqdm, jupyter), e.g.:
```
conda create -y -n napari-env -c conda-forge python=3.10
conda activate napari-env

conda install -c conda-forge napari pyqt h5py tqdm jupyter
```

## Usage
Run the jupyter notebook `ReFLeCT_4D_visualization.ipynb`, modifying the file path depending on where you downloaded the above 4D datasets. Note that the script requires decompressing and loading all the 3D volumes into computer memory -- feel free to load fewer time points in RAM-scarce situations.

Use the interactive capabilites of napari to rotate the 3D perspective of the organism and advance through time using the bottom slider. You can also switch to 2D cross-sectional views (ctrl+y) and use the bottom sliders to advance through space and time.
