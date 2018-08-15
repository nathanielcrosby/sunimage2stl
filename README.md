# sunimage2stl
A python package that turns 2D images of the Sun into 3D printable models in .stl file form.
I created this while interning at the Harvard-Smithsonian Center for Astrophysics.
It is intended to create hemispherical 3D prints of the whole sun and flat 3D prints of specific features of the sun (ex. solar flares).
These are to be used for educational purposes, specifically for the visually impaired.
Currently, the full Sun Model is exclusively for XRT data while the partial sun model is for any .png file.

## Getting Started
 ### Prerequisites
  - os
  - subprocess
  - numpy
  - matplotlib
  - scipy
  - skimage
  - stl_tools
  - numpy-stl
  - imageio
  
### Installing
  1. ```pip install sunimage2stl```
  
  OR
  
  1. ```mkdir sunimage2stl```
  2. ```cd sunimage2stl```
  3.  ```git clone https://github.com/nathanielcrosby/3DSunModeling.git``` OR Download
  4. ```ls``` to make sure you see setup.py
  5. ```python setup.py install```
  6. go into a python window and ensure everything can be imported and is working properly by testing some examples
  
### Examples
See wiki....
https://github.com/nathanielcrosby/sunimage2stl/wiki

## Authors
  Nathaniel Crosby
