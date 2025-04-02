# CS-4476 Project 1: Convolution and Hybrid Images
# Hybrid Image Generator

## 📷 Overview
This project implements hybrid image generation — combining the **low-frequency content** of one image with the **high-frequency content** of another to produce an image that changes interpretation based on viewing distance.

The project is based on the SIGGRAPH 2006 paper: *Hybrid Images* by Oliva, Torralba, and Schyns.

---

## 🧠 Key Concepts
- **Convolution and Image Filtering** using NumPy and PyTorch
- **Gaussian Kernel Construction** (1D and 2D)
- **Hybrid Image Synthesis** with low-pass and high-pass filtering
- **Fourier Domain Deconvolution** (optional extra credit)
- **Performance Comparison** between NumPy and PyTorch backends

---

## 💻 Project Structure

### ✅ Part 1: NumPy
- `create_Gaussian_kernel_1D()`: Generates 1D Gaussian filter
- `create_Gaussian_kernel_2D()`: Forms 2D filter via outer product
- `my_conv2d_numpy()`: Manually implements 2D convolution
- `create_hybrid_image()`: Combines low-pass and high-pass images

### 🔥 Part 2: PyTorch
- `HybridImageDataset`: PyTorch Dataset to load image pairs and cutoff frequencies
- `HybridImageModel`: PyTorch model that replicates the hybrid image creation process
- Uses `torch.nn.functional.conv2d()` for fast filtering

### 🧪 Part 3: Convolution Analysis
- `my_conv2d_pytorch()`: Re-implements convolution using PyTorch
- Tests effect of different **stride**, **padding**, and **grouping** values on convolution output shape

### 🌊 Part 4 (Extra Credit): Frequency Domain
- `my_conv2d_freq()`: Performs convolution using 2D Fourier Transform
- `my_deconv2d_freq()`: Attempts to deblur image by deconvolving in frequency domain

---


## Getting Started

- See Project 0 for detailed environment setup. This project's environment is set up similarly, and will create a conda environment called `cv_assn1`.
- Ensure that you are using the environment `cv_assn1`, which you can install using the install script `conda/install.sh`, or the following scripts:

```bash
# create a conda environment named cv_assn1
conda env create -f ./conda/environment.yml -y
# activate the environment
conda activate cv_assn1
# install the source code in dev mode
pip install -e .
```


## Important Notes

- Please follow the environment setup in Project 0.
- Do **not** use absolute paths in your code or your code will break.
- Use relative paths like the starter code already does.
- Failure to follow any of these instructions will lead to point deductions. Create the zip file by clicking and hand it in with your report PDF through Gradescope (please remember to mark which parts of your report correspond to each part of the rubric).

## Project Structure

```console
.
├── README.md
├── cutoff_frequencies.txt
├── data
│   ├── 1a_dog.bmp
│   ├── 1b_cat.bmp
│   ├── 2a_motorcycle.bmp
│   ├── 2b_bicycle.bmp
│   ├── 3a_plane.bmp
│   ├── 3b_bird.bmp
│   ├── 4a_einstein.bmp
│   ├── 4b_marilyn.bmp
│   ├── 5a_submarine.bmp
│   └── 5b_fish.bmp
│   └── part4
│       ├── kernel.npy
│       └── mystery.npy
├── docs
│   └── report.pptx
├── project-1.ipynb
├── pyproject.toml
├── scripts
│   └── submission.py
├── setup.cfg
├── src
│   └── vision
│       ├── __init__.py
│       ├── part1.py
│       ├── part2_datasets.py
│       ├── part2_models.py
│       ├── part3.py
│       └── utils.py
└── tests
    ├── __init__.py
    ├── __pycache__
    ├── test_part1.py
    ├── test_part2.py
    ├── test_part3.py
    └── test_utils.py
```
