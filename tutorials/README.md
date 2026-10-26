# FLMNH Digital Imaging Workshop
**3D GMM in 3D Slicer** 
Note: **Highlighted text** contains steps where you will interpret morphology. Pay extra attention to these when working with your own data.

**Steps**
1. Install 3D Slicer
    - a. https://download.slicer.org/
2. Open 3D Slicer
3. Open the Extensions Manager module (puzzle piece icon in main navigation bar)

<p align="center">
<img src="images/fig-000.png" width = 600>
</p>

4. Install SlicerMorph
    - a. Click “Install Extensions” tab
    - b. Search for “SlicerMorph”
    - c. Click “Install”

<p align="center">
<img src="images/fig-001.png" width = 600>
</p>

    - d. Click “Restart” to restart Slicer and begin using SlicerMorph

<p align="center">
<img src="images/fig-003.png" width = 600>
</p>

    - e. Detailed instructions
        - i. https://github.com/SlicerMorph/SlicerMorph#installation
5. Leave 3D Slicer
6. Open your web browser
7. Download sample data from the tutorial GitHub repo
    - a. Navigate to the Mouse_Models tutorial repository
        - i. https://github.com/aubricot/Mouse_Models/tree/main
    - b. Click the  “Code” dropdown menu
    - c. Click “Download Zip”

<p align="center">
<img src="images/fig-005.png" width = 600>
</p>

8. Extract the files for GMM
    - a. Locate “Mouse_Models-main.zip” in your Downloads folder
    - b. Right click and extract the file (varies by operating system)
    - c. Open Mouse_models-main folder

<p align="center">
<img src="images/fig-006.png" width = 600>
</p>

9. **Inspect the mouse data - Most 3D geometric morphometrics pipelines require your data to follow this format**
    - a. Directory structure
        - i. Main directory (Mouse_models-main)
            - 1. LMs (all landmarks in one folder)
            - 2. Models (all models in one folder)
    - b. File names
        - i. Landmark and model files should only differ in their extension
            - 1. Example
                - a. LMs/A_J.mrk.json
                - b. Models/A_J.ply

<p align="center">
<img src="images/fig-007.png" width = 600>
</p>

    - c. When creating your own GMM data, be sure to keep this structure
10. Return to 3D Slicer
11. Open the GPA submodule from SlicerMorph
    - a. Go to the Module List dropdown
    - b. Go to SlicerMorph
        - i. Geometric Morphometrics
            - 1. GPA

<p align="center">
<img src="images/fig-008.png" width = 600>
</p>

12. Load the landmark files
    - a. Click “Select Landmark Files”
    - b. Choose the “LMs” folder you downloaded from GitHub

<p align="center">
<img src="images/fig-009.png" width = 600>
</p>

    - c. Select all files in the “LMs” folder
    - d. Click Open

<p align="center">
<img src="images/fig-010.png" width = 600>
</p>

13. Click the “View selected landmark files” tab to check that they loaded

<p align="center">
<img src="images/fig-011.png" width = 600>
</p>

14. Click “Select output directory”
    - a. Navigate to “Mouse_Models-main”
    - b. Create a new folder, “GMM”
    - c. Select “GMM” and hit “Choose”

<p align="center">
<img src="images/fig-012.png" width = 600>
</p>

15. Click “Covariate options”
    - a. Select covariates table: demo_metadata.csv
        - i. This is a table with mock metadata for this tutorial
        - ii. This is used to color PCA points by species, age, collection locality, etc.
16. Click “Execute GPA + PCA”
    - a. GPA is Generalized Procrustes Analysis
        - i. It is a superimposition strategy to align and scale meshes
        - ii. This minimizes position and shape variation, so GMM analysis can focus on shape differences
    - b. PCA is Principal Component Analysis
        - i. It is a covariance analysis to condense landmarks into independent shape axes, which form the morphospace used to plot and compare specimens

<p align="center">
<img src="images/fig-014.png" width = 600>
</p>

17. Confirm that GPA + PCA succeeded
    - a. You should see outputs in the “GPA Module Log Information” tab, and in the three viewer windows on the bottom right side of the screen

<p align="center">
<img src="images/fig-015.png" width = 600>
</p>

    - b. To see output files, click “View Output Files”
        - i. These files can be loaded into Slicer in a new session to resume analysis

<p align="center">
<img src="images/fig-016.png" width = 600>
</p>

18. Switch to the “Results” tab

<p align="center">
<img src="images/fig-017.png" width = 600>
</p>

19. Plot landmark variance
    - a. This plot shows how much variation is present in your dataset at each landmark
    - b. Click “Plot LM variance”
        - i. You may need to use the “Center view” button and zoom in/out (scroll wheel) until the landmark variance points show up in the 3D viewer
    - c. **Inspect which landmarks are most and least variable in XYZ directions**
        - i. If you don’t see landmark labels on the 3D plot, adjust settings below
            - 1. Click and rotate the landmark variance points
            - 2. Adjust “Scale Glyphs” to show labels on points
        - ii. For example, landmark 14 (yellow oval along skull midline) is long and skinny
            - 1. It  looks very variable anteroposteriorly, but not very variable laterally
        - iii. Identify another landmark variance plot and try to morphologically interpret what its shape means

<p align="center">
<img src="images/fig-019.png" width = 600>
</p>

<p align="center">
<img src="images/fig-020.png" width = 600>
</p>

20. Plot the PCA scatterplot
    - a. Plot PC1 v PC2
        - i. X Axis: PC 1
        - ii. Y Axis: PC 2
        - iii. Select factor: diet
            - 1. This allows you to color points by species, age, collection locality, etc.
        - iv. Click “Scatter Plot”
    - b. Inspect explained proportion of variance values

<p align="center">
<img src="images/fig-021.png" width = 600>
</p>

    - c. Inspect PCA plot in blue window on right
        - i. Click “Maximize view” icon to make the PCA plot full screen
        - ii. Zoom in and out with your scroll wheel
    - d. **Inspect which points are close and far in PC morphospace**
        - i. Points that are closer together are more similar in shape
        - ii. Separation along a PC means the specimens differ in the trait for that axis
            - 1. For example, specimen C57BLKs is the max shape for PC1 (right side of plot) and specimen C3H_HEJ is the min shape (left side)
            - 2. These are the min and max of the trait captured by PC1
                - a. If PC1 captures elongation, the min shape would be short and the max shape would be long
        - iii. Find the min and max shapes of PC2
            - 1. What shape trait might PC2 capture? Inspect the min and max shapes and make a guess
        - iv. Click “Restore View Layout” icon to return to multipanel view

<p align="center">
<img src="images/fig-022.png" width = 600>
</p>

<p align="center">
<img src="images/fig-023.png" width = 600>
</p>

21. Plot lollipop vectors
    - a. Lollipop vectors show shape change along trajectories
        - i. In 3D Slicer, they are shown by PC, allowing you to show variance for a landmark along PC’s
    - b. Look at lollipop vectors for PC1 v PC2
        - i. Vector One: PC1
        - ii. Vector Two: PC2
        - iii. Click “Lollipop Vector Plot”

<p align="center">
<img src="images/fig-024.png" width = 600>
</p>

    - c. Click “Maximize view” icon to make lollipop plot full screen

<p align="center">
<img src="images/fig-026.png" width = 600>
</p>

    - d. **Look at landmark 14 (also discussed in 18.c.ii)**
        - i. Inspect PC1 (red) and PC2 (green) vectors
            - 1. Which direction does PC1 vary in?
                - a. What morphological change could this correspond to?
            - 2. Which direction does PC2 vary in?
                - a. What morphological change could this correspond to?
    - e. Click “Restore View Layout” icon to return to multipanel view
22. Return to the “Setup Analysis” tab
    - a. Scroll down to “GPA Module Log Information”
    - b. Check “Closest sample to mean” in log outputs
        - i. We are going to load this specimen and landmarks into view in the “Interactive 3D” tab
            - 1. For this data, the specimen is FVB_NJ
23. Switch to the “Interactive 3D” tab
    - a. Specify reference model: FVB_NJ.ply
        - i. Or the path to your specimen closest to mean from 21.b above
    - b. Specify LM set for the selected model: FVB_NJ.mrk.json
        - i. Or the path to your specimen closest to mean from 21.b above
    - c. Active warp source: PCA
    - d. Click “Apply”

<p align="center">
<img src="images/fig-027.png" width = 600>
</p>

    - e. The left panel shows your reference model warped to the mean using the PCA mean landmark configuration
    - f. The right panel shows the actual reference specimen and landmarks
24. Adjust “PCA Visualization Parameters”
    - a. **Watch the blue model warp along PCs using parameters you set here to understand morphospace trends**
    - b. Magnification Factor: 5.00
        - i. This updates the magnification of PCA warping to 3 SD’s from the mean
        - ii. We are using a high value to make visualizing changes in lab mice easier. For most non-biomedical/model organism datasets, 1.00-3.00 is plenty
    - c. Slider warps: 1
        - i. This warps the specimen along PC1
    - d. PC X Slider
        - i. Adjust the slider to see min and max shapes along chosen PC
            - 1. **What shape changes do you notice across PC1?**

<p align="center">
<img src="images/fig-029.png" width = 600>
</p>

    - e. Optional
        - i. Check “Drive 3D model from PCA scatter plot”
        - ii. Click a point in the PCA Scatter Plot
        - iii. Watch the blue (reference) model warp using the landmark configuration of the selected point

<p align="center">
<img src="images/fig-030.png" width = 600>
</p>

25. Under, “Setup Interactive Visualization”
    - a. Active warp source: Geomorph LR
26. Switch to the “Geomorph Linear Regression” tab
    - a. Rscript path: /usr/lib/R/bin/Rscript
            - 1. Point to your Rscript file
        - i. Click “Refresh status”
        - ii. Click “Launch Rserve”
        - iii. Click “Connect”

<p align="center">
<img src="images/fig-032.png" width = 600>
</p>

    - b. Check that status checks passed for Rscript, Rserve, and Connection

<p align="center">
<img src="images/fig-034.png" width = 600>
</p>

27. **Start with a basic linear model in “R Formula”**
    - a. Coords ~ Size
        - i. shape (the Procrustes coordinates, Coords) as a function of size
        - ii. Nul/basel model: is shape explained by size alone?

<p align="center">
<img src="images/fig-035.png" width = 600>
</p>

    - b. Click “Fit model in R (procD.lm)

<p align="center">
<img src="images/fig-036.png" width = 600>
</p>

    - c. See the model as a shape change
        - i. Go to “Coefficient Visualization Parameters”
            - 1. Magnification factor: 10.00
            - 2. Click “Update Magnification”
            - 3. Adjust the slider and view shape change for the warped mesh

<p align="center">
<img src="images/fig-037.png" width = 600>
</p>

28. Add a grouping variable to see if groups differ
    - a. Coords ~ Size + collection_locality
        - i. + fits main effects only
        - ii. common slopes: groups differ in mean shape but share the size trend
    - b. Coords ~ Size * collection_locality
        - i. * is shorthand for main effects plus their interaction
            - 1. Size * locality expands to Size + locality + Size:locality
        - ii. Unique slopes: groups also differ in how shape changes with size
29. Congrats! You’ve completed the 3D GMM in 3D Slicer tutorial
    - a. Be sure to check out SlicerMorph Tutorial for more information
        - i. https://github.com/SlicerMorph/Tutorials/tree/main
30. To continue with some other classic geometric morphometric analysis from R geomorph (Adams et al. 2025), check out the demo on Google colab and the R script in the tutorial GitHub
    - a. https://github.com/aubricot/Mouse_Models/tree/main
