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

## View controls
Use the `Zoom` button to zoom in and out (via +/- controls or a dropdown menu). 
Adjust line thickness with `LW` and font size with `FS`.
You can also pan the view in any direction, including diagonally, using a trackpad.
Pinch-to-zoom is not supported due to Tkinter limitations.
Instead, hold Ctrl and scroll (mouse wheel or two-finger gesture, vertical or horizontal) to zoom.

## Managing cropped regions

- **Delete regions**
Right-click a rectangle to delete it. You will be prompted for confirmation before deletion.

<dl>
  <dt>Count regions</dt>
  <dd>Click the `COUNT` button to print region counts by label to the terminal where the program was launched.</dd>
  <dt>Renumber regions</dt>
  <dd>Click the `RENUMBER` button to renumber labels after deletions.</dd>
  <dt>Save screenshots</dt>
  <dd>Click the `SAVE SS` button to save a screenshot to the output directory specified at launch.</dd>
  <dt>Generate HTML preview</dt>
  <dd>Click the `HTML` button to generate a thumbnail preview HTML file (rois.html) in the output directory specified at launch.</dd>
</dl>

## Output structure

<dl>
<dt>Directory names</dt>
<dd>Cropped regions are saved in label-specific subdirectories within the output directory. Each label i corresponds to a subdirectory named "Category i".</dd>
<dt>Filenames</dt>
<dd>Each cropped region is saved with a filename in the format "xxxx-Ci-N-x0-y0-x1-y1-w-h.png".
Here, xxxx is inherited from the source image filename, Ci indicates the label (with i representing the label index), and N is a sequential number assigned to each region. 
(x0, y0) and (x1, y1) denote opposite corners of the rectangle, while w and h indicate its width and height.
Filenames are designed to be as unique as possible, making it easy to combine cropped regions from different source images.
</dd>
</dl>

## Implementation
This tool is implemented in Python using Tkinter for the graphical interface.
On macOS, it also uses tkmacosx to provide native-like UI behavior.

