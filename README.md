# Image-patch
Image-patch is an interactive tool for extracting and labeling rectangular regions from images.
While the application is launched from the command line, the main workflow is performed through mouse-based operations.
Users can drag to select regions, assign labels (0–20), and visualize them with color-coded overlays.  
The extracted regions can be organized and used as training data for machine learning workflows.

## Screenshot

<kbd><img src="img/screenshot.jpg"></kbd>

Screenshot using an image from [Takeda et al. (2020)](https://doi.org/10.1136/jclinpath-2020-206801).

## Command line usage
```4d
% image_patch.py image-filename output-directoryname 
```

## Cropping with the mouse
Drag the mouse to select a rectangular region. 
Rectangular regions can be selected as either squares or rectangles ("Sqr" or "Rect").
Labels can be assigned from 0 to 20, and each rectangle is drawn in a corresponding color on the image.


