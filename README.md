# 3D Geometric Morphometrics in 3D Slicer   
Digital Imaging Workshop: Florida Museum of Natural History   
27 October 2026    

See [`tutorials/`](tutorials/) for the workshop workflow.

## Contents

| Path | Description |
| --- | --- |
| `Models/` | 62 mouse cranium surface models (`.ply`), one per specimen |
| `LMs/` | 62 mouse cranium landmarks (`.mrk.json`), one per specimen |
| `mouse_models_factors.csv` | Demo specimen metadata for coloring PCA plots |
| `tutorials/` | Workshop workflow |
| `mouse_gmm_demo.ipynb` | R geomorph demo in Google Colab |

### Geomorph demo in Google Colab
:arrow_right: 💮: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/aubricot/Mouse_Models/blob/main/mouse_gmm_demo.ipynb) Click here to try out R geomorph.

### A note on `mouse_models_factors.csv`

The `collection_locality`, `diet`, and `strain` columns are **fabricated** for teaching purposes only. They exist so workshop participants can practice coloring and grouping points in morphospace, and should not be cited or reused as real specimen data. The `specimen_id` column matches the `Models/` filenames so the table joins directly onto GPA output.

### Mouse_Models
Forked from [SlicerMorph/Mouse_Models](https://github.com/SlicerMorph/Mouse_Models)

## Additional resources

### Software

* **3D Slicer** — https://download.slicer.org/
* **SlicerMorph** — https://slicermorph.org
* **geomorph** (geometric morphometrics in R) — https://cran.r-project.org/web/packages/geomorph/index.html
  * Tutorial playlist — https://www.youtube.com/watch?v=X0XK2cucJnc&list=PLArEOEE-THY4GSpBCuqi-jiw-XBRm7ef-&index=5

### Tutorials

* **SlicerMorph tutorials on GitHub** — https://github.com/SlicerMorph/Tutorials
  * GPA module I — https://github.com/SlicerMorph/Tutorials/tree/main/GPA_1
  * GPA module II — https://github.com/SlicerMorph/Tutorials/blob/main/GPA_2
  * GPA module III — https://github.com/SlicerMorph/Tutorials/blob/main/GPA_3
  * GPA module IV — https://github.com/SlicerMorph/Tutorials/blob/main/GPA_4
  * GPA module V — https://github.com/SlicerMorph/Tutorials/blob/main/heatmaps/README.MD
* **SlicerMorph on YouTube** — https://www.youtube.com/@slicermorphslicermorph8728/videos
  * GPA module — https://www.youtube.com/watch?v=FCeZ2J5Uvcw
  * Applying your own landmarks — https://www.youtube.com/watch?v=aazPHFZWMdA and https://www.youtube.com/watch?v=xrly9atx7xQ
* **Virtual Paleontologist on YouTube** — https://www.youtube.com/@VirtPaleo
  * 3D Slicer GMM walkthrough — https://www.youtube.com/watch?v=Y_Hibl8pU74

### Data

* **SlicerMorph mouse models and landmarks** (upstream of this fork) — https://github.com/SlicerMorph/Mouse_Models/tree/main

### Getting help

The 3D Slicer forum and the lists below are good places to go when you get stuck. People are responsive and friendly, and the lists also carry announcements about workshops, conferences, and jobs.

* **3D Slicer forum** — https://discourse.slicer.org/
* **SlicerMorph announcements** — https://mailman21.u.washington.edu/mailman/listinfo/slicermorph-announcements
* **Geometric morphometrics (morphmet2)** — https://groups.google.com/g/morphmet2
* **geomorph R package** — https://groups.google.com/g/geomorph-r-package

## Upstream

Datasets that are used in SlicerMorph tutorials and [Zhang et al. (2022) Automated landmarking via multiple templates. Plos One.](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0278035)

[![DOI](https://zenodo.org/badge/430023741.svg)](https://zenodo.org/badge/latestdoi/430023741)
