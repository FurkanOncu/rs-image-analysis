# Research Skills: Image Analysis

**Course:** Research Skills — Image Analysis (800877-M-3) | Tilburg University, Block 3, Spring 2026  
**Author:** Furkan Öncu  
**Language:** Python (Jupyter Notebook)  
**Libraries:** `scikit-image`, `scipy`, `numpy`, `matplotlib`

---

## Project Overview

This repository contains two individual take-home assignments covering core image analysis techniques. Both parts apply the same processing pipeline to two real-world color images of flowers (`rgbimage1.jpg`, `rgbimage2.jpg`).

The work demonstrates practical application of color space theory, spatial filtering, and image segmentation using Python's `scikit-image` ecosystem.

---

## Part 1 — Color Spaces & Spatial Filtering (45 pts)

### Task 1A: RGB ↔ HSV Conversion
- Loaded and displayed two color images with appropriate titles
- Converted RGB images to HSV; separated and visualized H, S, V channels alongside R, G, B channels in subplots with intensity histograms
- Identified which channels share similar intensity distributions between the two images and described the point operation applied
- Applied **histogram equalization** to the Hue channels; displayed results as grayscale with updated histograms
- Reconstructed full RGB images using the equalized Hue channel with original S and V; saved outputs
- Explained why intensity transformation in a single channel (Hue) produces changes in the full RGB image

### Task 1B: Image Smoothing with Gaussian Kernels
- Converted color images to grayscale
- Applied `scipy.ndimage.gaussian_filter` with σ ∈ {1, 2, 4, 8, 16, 32, 64}
- Recorded execution time for each σ using Python's `time` module
- Displayed all blurred images in subplots; plotted time-vs-sigma curve
- Commented on observed relationship between kernel size and both visual smoothing and computation time

---

## Part 2 — Image Segmentation (40 pts)

### Task 2A: Flower Segmentation
1. **White flower segmentation** — designed a preprocessing and thresholding pipeline to produce a clean binary mask for white flowers; applied morphological operations and displayed results at each step
2. **Hole filling & quantification** — filled holes in the binary mask, automatically counted the number of white flowers, and plotted a histogram of flower diameters
3. **Color replacement** — changed all white flowers to **Fandango** (RGB: 181, 51, 138) and saved the modified image
4. **Red/orange/yellow flower segmentation** — segmented warm-colored flowers using HSV thresholding and morphological cleanup; displayed step-by-step results
5. **Bounding box detection** — detected individual warm-colored flowers and overlaid bounding boxes on the original image; implemented without any hardcoded coordinates, working generically on both images

### Task 2B: Oral Examination (5 pts)
Completed a 5-minute individual online oral check with the course lecturer.

---

## Repository Structure

```
rs-image-analysis/
│
├── assignment_1_Furkan_Oncu.ipynb   # Part 1: Color spaces & spatial filtering
├── assignment2_Furkan_Oncu.ipynb    # Part 2: Segmentation & analysis
└── README.md
```

> **Note:** Input images (`rgbimage1.jpg`, `rgbimage2.jpg`) are not included due to course data policy.

---

## Key Techniques

| Technique | Function / Tool |
|---|---|
| Color space conversion | `skimage.color.rgb2hsv`, `hsv2rgb` |
| Histogram equalization | `skimage.exposure.equalize_hist` |
| Gaussian smoothing | `scipy.ndimage.gaussian_filter` |
| Thresholding | Manual HSV range thresholding |
| Morphological operations | `skimage.morphology` (erosion, dilation, closing, hole filling) |
| Connected components | `skimage.measure.label`, `regionprops` |
| Bounding boxes | `skimage.measure.regionprops` |

---

## How to Run

1. Clone the repository
2. Install dependencies: `pip install scikit-image scipy matplotlib numpy`
3. Place `rgbimage1.jpg` and `rgbimage2.jpg` in the same directory
4. Open and run each notebook end-to-end (`Run All`)

---

## Notes on AI Use

Generative AI tools were used in parts of this assignment in accordance with course policy. All AI-assisted code was reviewed, understood, and declared in the submission file as required.
