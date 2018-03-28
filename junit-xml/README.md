# Conda package for junit-xml

https://anaconda.org/cctbx/junit-xml

https://pypi.python.org/pypi/junit-xml

Rebuild because conda package in bioconda channel does not support Windows.
Also removes dependency on bioconda channel

1) Create initial matplotlib/meta.yaml
   ```
   conda skeleton pypi junit-xml
   ```

2) Edit junit-xml/meta.yaml

   a) Clean up `about: description:`.

   b) Update recipe-maintainers

3) Build package (in directory containing junit-xml directory)
   ```
   conda build --python 2.7 junit-xml
   ```

4) Upload
   ```
   anaconda login
   anaconda upload -u cctbx junit-xml-<build version>.tar.bz2
   ```

Steps 1-2 are only for creating the initial directory and meta.yaml for the
matplotlib package. Steps 3-4 are for building and updating the package on
the cctbx channel.
