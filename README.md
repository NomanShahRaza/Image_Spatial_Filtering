<div align="center">

# 🖼️ Image Spatial Filtering

### A practical exploration of image enhancement, edge detection, and sharpening in the spatial domain.

![Digital Image Processing](https://img.shields.io/badge/Domain-Digital%20Image%20Processing-2563EB?style=for-the-badge)
![Spatial Filtering](https://img.shields.io/badge/Focus-Spatial%20Filtering-7C3AED?style=for-the-badge)
![Python and Jupyter](https://img.shields.io/badge/Tools-Python%20%7C%20Jupyter-F59E0B?style=for-the-badge)

**Explore how neighborhood-based filters transform images — from smoothing and noise reduction to edge extraction and detail enhancement.**

[Repository](https://github.com/NomanShahRaza/Image_Spatial_Filtering) · [Report an issue](https://github.com/NomanShahRaza/Image_Spatial_Filtering/issues)

</div>

---

## 📌 Overview

**Image Spatial Filtering** is a hands-on digital image processing project demonstrating how spatial-domain filters modify an image using the intensity values of neighboring pixels.

The repository explores three key areas:

- **Smoothing:** reduce noise and fine details using Average and Gaussian filters.
- **Edge detection:** highlight object boundaries using Prewitt, Sobel, Laplacian of Gaussian (LoG), Derivative of Gaussian, and Canny.
- **Image sharpening:** enhance fine details and edges using Laplacian-based sharpening and unsharp masking.

The project includes Python scripts and Jupyter notebooks for experiments **with and without normalization**.

## 🧭 Contents

- [What is spatial filtering?](#-what-is-spatial-filtering)
- [Filters explored](#-filters-explored)
- [Visual results](#-visual-results)
- [Repository structure](#-repository-structure)
- [Getting started](#-getting-started)
- [Learning outcomes](#-learning-outcomes)
- [Author](#-author)

## 🔍 What is spatial filtering?

Spatial filtering is a neighborhood operation performed directly on image pixels. The output value at a pixel is calculated from that pixel and the values of pixels in its surrounding neighborhood.

A filter applies a mathematical operation through a **kernel (mask)** as it moves across the image.

## 🧪 Filters explored

### 1. Smoothing filters

Smoothing filters are low-pass filters commonly used to reduce noise and small image details. They are also useful as a preprocessing step before further image analysis.

| Filter | Description | Key consideration |
|---|---|---|
| **Average filter** | Replaces a pixel with the average intensity of its neighborhood. | Simple, but larger neighborhoods can blur edges. |
| **Gaussian filter** | Applies a weighted neighborhood average using a Gaussian distribution. | Standard deviation controls smoothing; larger values produce stronger blur. |

<details>
<summary><strong>📷 View smoothing results</strong></summary>
<br>
<div align="center">
<img src="https://user-images.githubusercontent.com/84965044/153725509-e6b05c2d-996e-4ff0-8c27-23b6f9c6d2d6.jpg" width="48%" alt="Smoothing result 1">
<img src="https://user-images.githubusercontent.com/84965044/153725507-9a10222f-ae2b-4436-9b8a-8a306ad84953.jpg" width="48%" alt="Smoothing result 2">
</div>
</details>

### 2. Edge detection filters

Edge detectors identify boundaries and structural details by locating changes in image intensity.

| Filter | Detection approach | Key consideration |
|---|---|---|
| **Prewitt** | Estimates horizontal and vertical intensity gradients. | Computationally simple, but sensitive to noise and direction. |
| **Sobel** | Uses gradient kernels to detect horizontal and vertical edges. | Simple and useful, though detected edges may need thinning. |
| **Laplacian of Gaussian (LoG)** | Smooths the image and then applies a second-derivative operation. | Detects edges in multiple directions; complex corners and intensity variations can affect results. |
| **Derivative of Gaussian** | Smooths the image before applying directional derivatives. | Smoothing improves robustness to noise, but edge responses may need post-processing. |
| **Canny** | Uses a multi-stage edge detection process. | Useful edge maps, including in noisy conditions, but more computationally involved. |

#### Prewitt and Sobel

<div align="center">
<img src="https://user-images.githubusercontent.com/84965044/153727033-deb3420a-2417-4e9d-84cd-08480cba9851.jpg" width="48%" alt="Prewitt and Sobel result 1">
<img src="https://user-images.githubusercontent.com/84965044/153727029-b6d04d96-b6e9-4e3d-a88b-dba0dfbb03bd.jpg" width="48%" alt="Prewitt and Sobel result 2">
<p><em>Edge detection outputs before normalization.</em></p>
<img src="https://user-images.githubusercontent.com/84965044/153727358-34af10f0-a365-4348-8044-576130a84614.png" width="48%" alt="Normalized edge result 1">
<img src="https://user-images.githubusercontent.com/84965044/153727361-830df46d-6808-4345-81d4-ef3831f31ed6.png" width="48%" alt="Normalized edge result 2">
<p><em>Corresponding outputs after normalization.</em></p>
</div>

#### Laplacian of Gaussian (LoG)

<div align="center">
<img src="https://user-images.githubusercontent.com/84965044/153727363-9958bc1e-412c-4053-bcfd-6730d40dcc48.jpg" width="70%" alt="LoG edge response">
<p><em>LoG edge response.</em></p>
<img src="https://user-images.githubusercontent.com/84965044/153727326-35f4cb4b-2454-4410-8754-0531387d9c6d.png" width="70%" alt="Normalized LoG result">
<p><em>LoG output after normalization.</em></p>
</div>

#### Derivative of Gaussian

<div align="center">
<img src="https://user-images.githubusercontent.com/84965044/153727333-13d227d3-b6b9-4a38-b226-5826eb8e3e60.jpg" width="70%" alt="Derivative of Gaussian response">
<p><em>Derivative of Gaussian response.</em></p>
<img src="https://user-images.githubusercontent.com/84965044/153727337-c669045d-fa14-4fe9-9b11-fc23a695e69f.png" width="70%" alt="Normalized Derivative of Gaussian result">
<p><em>Output after normalization.</em></p>
</div>

#### Canny edge detector

The project also explores Canny edge detection with Otsu's thresholding for automatic threshold selection.

<div align="center">
<img src="https://user-images.githubusercontent.com/84965044/153727348-57f642a1-1f77-4456-a311-2d42c3e8fd1d.png" width="70%" alt="Canny edge detection result">
</div>

### 3. Image sharpening filters

Sharpening enhances fine details, lines, and edges that may appear blurred.

- **Laplacian-based sharpening:** uses a derivative filter to emphasize rapid intensity changes. Since derivative filters can amplify noise, this method is best applied to a suitably denoised image.
- **Unsharp masking:** blurs the original image, subtracts the blurred image to obtain a detail mask, and adds that mask back to the original image.

<div align="center">
<img src="https://user-images.githubusercontent.com/84965044/153727343-307b2c6a-445b-436b-b325-b800208c574f.jpg" width="75%" alt="Image sharpening result">
<p><em>Image sharpening using Laplacian and smoothing-based techniques.</em></p>
</div>

## 🗂️ Repository structure

```text
Image_Spatial_Filtering/
│
├── Images/
├── Spatial_Filtering_with_Normalization.ipynb
├── Spatial_Filtering_with_Normalization.py
├── Spatial_Filtering_without_Normalization.ipynb
├── Spatial_Filtering_without_Normalization.py
└── README.md
```

## 🚀 Getting started

### 1. Clone the repository

```bash
git clone https://github.com/NomanShahRaza/Image_Spatial_Filtering.git
cd Image_Spatial_Filtering
```

### 2. Explore the notebooks

**With normalization**
- [Open Jupyter Notebook](https://github.com/NomanShahRaza/Image_Spatial_Filtering/blob/main/Spatial_Filtering_with_Normalization.ipynb)

**Without normalization**
- [Open Jupyter Notebook](https://github.com/NomanShahRaza/Image_Spatial_Filtering/blob/main/Spatial_Filtering_without_Normalization.ipynb)

### 3. Run the Python scripts

- [Spatial_Filtering_with_Normalization.py](https://github.com/NomanShahRaza/Image_Spatial_Filtering/blob/main/Spatial_Filtering_with_Normalization.py)
- [Spatial_Filtering_without_Normalization.py](https://github.com/NomanShahRaza/Image_Spatial_Filtering/blob/main/Spatial_Filtering_without_Normalization.py)

> **Note:** A dependency list is not specified in this repository README. Check the imports in the notebook or Python scripts and install the required packages before running them.

## 🎯 Learning outcomes

- Understand neighborhood operations in the spatial domain.
- Compare uniform and Gaussian smoothing.
- Explore gradient-based and second-derivative edge detection.
- Observe how normalization changes the display of filter responses.
- Understand the trade-off between noise reduction, edge preservation, and sharpness.
- Compare Laplacian sharpening with unsharp masking.

## 👨‍💻 Author

<div align="center">

### Noman Shah Raza

**AI Specialist & Researcher**  
Artificial Intelligence · Machine Learning · Computer Vision · Digital Image Processing

[![GitHub](https://img.shields.io/badge/GitHub-NomanShahRaza-181717?style=for-the-badge&logo=github)](https://github.com/NomanShahRaza)

</div>

---

<div align="center">

**If you find this project useful, consider giving it a ⭐ on GitHub!**

<sub>Built for learning, experimentation, and exploring the fundamentals of digital image processing.</sub>

</div>
