# Week 4 Assignment: Filling Corrupted Frames Using Interpolation

## 📁 Project Overview

In this assignment, we worked on **filling corrupted/missing frames** from a 2D pose estimation dataset using **Gaussian filtering** and **interpolation techniques**. Our goal was to smooth noisy data and reconstruct missing frames using **Linear** and **Cubic Spline** interpolation methods.

---

## 📚 Dataset Information

We used the **[VideoPose3D](https://github.com/facebookresearch/VideoPose3D)** dataset from Facebook Research, specifically the 2D keypoints data.

- **Subject:** `S2`
- **Action:** `Walking 1`
- **Camera View:** `Camera 0`

### 📐 Data Shape

( 3236, 17, 2)


- **3236 frames** — Number of time steps (frames in the video).
- **17 joints** — Each frame contains 17 body keypoints.
- **2 coordinates** — Each keypoint has (x, y) positions in the image plane.

---

## 🎞 Initial Skeleton Video

We visualized the raw 2D keypoints as an animated video:

- 🔸 `skeleton_video.mp4`

However, we noticed **shaking/jittery movement** in the skeleton, likely due to noise.

---

## 🧹 Gaussian Filter for Smoothing

To reduce the noise, we applied a **temporal Gaussian filter** to smooth the keypoint trajectories across frames.

### ✅ How It Works

- Each joint's `(x, y)` time series is smoothed independently.
- A **Gaussian kernel** is applied over time for each coordinate.
- The **sigma (σ)** parameter controls the amount of smoothing.

### 🧮 Formula

Given a time series \( $$ x_t $$ \), the smoothed output \( $$ x̄_t $$ \) is:

$$
x̄_t = \sum_{k=-K}^{K} w_k \, x_{t+k}
$$

with weights:

$$
w_k = \frac{1}{\sqrt{2\pi}\sigma} \exp\left(-\frac{k^2}{2\sigma^2}\right)
$$

---

### 🎞 Smoothed Video

- 🔹 `smoothed_skeleton_video.mp4`  
- 🔸 `smooth_compare.mp4` – side-by-side comparison of raw vs. smoothed motion

---

## 🧩 Filling Missing Frames

We observed some **corrupted/missing frames** in the dataset. To restore these, we used two interpolation techniques:

### 🔹 Method 1: **Linear Interpolation**

- Implemented with `numpy.interp`
- Simple and fast
- Works well for small gaps

### 🔸 Method 2: **Cubic Spline Interpolation**

- Implemented with `scipy.interpolate.CubicSpline`
- More accurate for natural motion
- Needs at least 2 known frames on each side

### 🧠 Interpolation Logic

- A **binary mask** detects missing values.
- For each missing frame:
  - Search for neighboring valid frames
  - If enough neighbors:
    - Apply linear or cubic interpolation
  - Otherwise: skip (cannot reliably interpolate)

---

## 🎞 Reconstructed Videos

- 🔸 `side_by_side_comparison_linear.mp4`  
- 🔹 `side_by_side_comparison_cubic.mp4`  

These videos compare original vs. reconstructed sequences for both interpolation methods.

---

## 📌 Key Learnings

- Temporal filtering (like Gaussian) is crucial for noise reduction in motion capture data.
- Interpolation helps recover corrupted sequences, improving continuity.
- Cubic interpolation performs better for smoother results, though it’s more computationally intensive.

---
