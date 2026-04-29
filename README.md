# Image-patch
Image-patch is an interactive tool for extracting and labeling rectangular regions from images.
While the application is launched from the command line, the main workflow is performed through mouse-based operations.
Users can drag to select regions, assign user-defined numerical labels, and visualize them with color-coded overlays.
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

## Managing cropped regions

<dl>
  <dt>Delete regions</dt>
  <dd>Right-click a rectangle to delete it. You will be prompted for confirmation before deletion.</dd>
  <dt>Count regions</dt>
  <dd>Click the "COUNT" button to print region counts by label to the terminal where the program was launched.</dd>
  <dt>Renumber regions</dt>
  <dd>Click the "RENUMBER" button to renumber labels after deletions.</dd>
  <dt>Save screenshots</dt>
  <dd>Click the "SAVE SS" button to save a screenshot to the output directory specified at launch.</dd>
  <dt>Generate HTML preview</dt>
  <dd>Click the "HTML" button to generate an HTML file (rois.html) with thumbnail previews</dd>
</dl>

