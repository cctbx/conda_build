# Conda package for matplotlib

https://anaconda.org/cctbx/matplotlib

https://matplotlib.org/index.html

https://pypi.python.org/pypi/matplotlib

Rebuild because default conda package also installs PyQt.
We want wxPython and Pyside2 (`conda-forge` channel is required)

1) Create initial matplotlib/meta.yaml
   ```
   conda skeleton pypi matplotlib
   ```

2) Edit matplotlib/meta.yaml

   a) Add default conda compilers
      ```
      requirements:
        build:
          - {{ compiler('cxx') }}
      ```
   b) Add wxpython and pyside2 to `host:` and `run:`
      ```
        - wxpython =3.0.0
        - pyside2 =5.6
      ```

   c) Clean up `about: description:`. Add text about linking to wxPython instead
      of PyQt

   d) Update recipe-maintainers

3) Build package (in directory containing matplotlib directory)
   ```
   conda build --python 2.7 matplotlib
   ```

4) Upload
   ```
   anaconda login
   anaconda upload -u cctbx matplotlib-<build version>.tar.bz2
   ```

Steps 1-2 are only for creating the initial directory and meta.yaml for the
matplotlib package. Steps 3-4 are for building and updating the package on
the cctbx channel.
