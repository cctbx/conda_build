# Repository for building CCTBX and dependencies as conda packages

https://anaconda.org/cctbx

https://github.com/cctbx

The goal is to use as many default conda packages as possible, and only build
things that are missing or that require some changes. These packages will reside
in the `cctbx` channel to avoid conflicts.

Channel resolution order will be used to prioritize CCTBX packages over default
conda packages.

`conda-forge` channel dependencies:
- PySide2

`bioconda` channel dependencies (probably roll into cctbx channel):
- junit-xml

## Installation

Modify your `~/.condarc` file so that it contains the following channels in
the following order.
```
channels:
  - cctbx
  - defaults
  - conda-forge
  - bioconda
```

Run `conda install cctbx_dependencies`
