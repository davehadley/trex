# TREx TPC Reconstruction

A stand-alone port of T2K-ND280 TPC reconstruction code (TREx).
The ND280 version is hosted at <https://git.t2k.org/nd280/recon/trexRecon>.
The original motivation for this port was to use the reconstruction for High-Pressure TPC R&D (see: <https://github.com/jthaigh/hptrex>). 
However, the reconstruction code is stand alone may be generally useful for any gaseous TPC experiment.

# Build Instructions

It is recommended to build with `conda`.

```
conda env create -f environment.yml
conda activate trex
cd src && make
```

# Run Instructions

TODO


# Development Instructions

Please install the pre-commit hooks before developing the code.

```
pre-commit install
```
