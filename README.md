# sunimage2stl
A python package that turns 2D images of the Sun into 3D printable models in .stl file form.
I created this while interning at the Harvard-Smithsonian Center for Astrophysics.
It is intended to create hemispherical 3D prints of the whole sun and flat 3D prints of specific features of the sun (ex. solar flares).
These are to be used for educational purposes, specifically for the visually impaired.
Currently, the full Sun Model is exclusively for XRT data while the partial sun model is for any png file.

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

#### Full Sun

The Full Sun aspect is entirely HINODE XRT data. A date should be given and then the program will find the nearest image.

All Full Sun Commands Start With:
```
  date = '2014/05/16'
  r = 460. #px

  image, header, x, y, z = sunimage2stl.3DPlot.image_to_xyz_mesh(date, r=r, base_len=228.6, offset_x=0., offset_y=0., 
  scale_factor_percent=0.25, minimum_intensity_threshold=0.45, buffer_zone=0., buffer_val=1.1,
  buffer=True, exp=2.0, scale_bool=True, earth=True, interval=2., local=True, index=2, flat_base=False)
```
To Do any of the Following just add these lines:

  3D Full Sun .stl File:
  ```
  sunimage2stl.3DPlot.stl_mesh_maker(x, y, z, interval=1, fname='test1.stl')
  ```
  
  3D Full Sun Movie:
  ```
  sunimage2stl.3DPlot.make_movie(x, y, z, image, file='movie.gif', fps=30, st_ang=0, en_ang=360, 
  st_elev_ang=90, en_elev_ang=0, time=10)
  ```
  
  3D Full Sun 3D Plot:
  ```
  sunimage2stl.3DPlot.ThreeDPlot(x, y, z, image, stride=10, figx=10., figy=10., save=False, file='3d.png')
  ```
  
  2D Full Sun .stl File:
  ```
  sunimage2stl.3DPlot.image_to_flat_stl(date, scale=100., width=100., depth=100., height=20.)
  ```
  
#### Partial Sun  
  
  These require a .png file as the "file" input. 
  - An image should be chosen 
  - Cropped to the proper size
  - Exported as a .png
  - file is then set to the image name
  
  2D Partial Sun .stl File:
  ```
  file = '2012_04_16__17_38_56_12__SDO_AIA_AIA_304' #.png
  sunimage2stl.ImagePlot.stl_file_maker(file, interval=2, threshold=0.35, fname='test.stl', gaussian=1)
  ```
  
  2D Partial Sun Plot:
  ```
  file = '2012_04_16__17_38_56_12__SDO_AIA_AIA_304' #.png
  sunimage2stl.ImagePlot.TwoDPlot(file, save=False)
  ```
## Authors
  Nathaniel Crosby
