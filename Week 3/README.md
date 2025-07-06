# Week 3 Assignment: Fourier Series and Signal Denoising

## 📘 Overview

In this exercise, we explored the **Fourier Series** and its powerful applications in **signal processing**, especially in the context of **animation and motion capture**.

The Fourier Series allows us to express any **periodic function** as a sum of simple sinusoids (sines and cosines). Even discontinuous functions like a **square wave** can be represented using continuous sine waves—showing how the frequency domain offers deep insight into signal behavior.

---

## 🧠 Key Concepts

- **Fourier Series**: Decomposes periodic signals into sinusoidal components.
- **Fourier Transform**: Generalizes this idea for non-periodic signals.
- **Frequency Domain Analysis**:
  - Low frequency → Smooth, slow-changing signals
  - High frequency → Rapid, jittery, or noisy signals

---

## 🧪 Simulation and Visualization

We implemented code to:
- Simulate a **square wave**
- Approximate it using **Fourier Series**
- Visualize how sinusoids add up to form a complex shape

> _"This shows how even jagged, piecewise signals can be built from smooth, continuous components."_  

---

## 🎮 Relevance to Animation

In animation, everything is a **signal**—whether it's:
- A character's hand motion
- A bouncing ball
- A changing facial expression

Fourier analysis helps in:
- 🎚 **Filtering**: Remove unwanted noise
- 🗜 **Compression**: Keep only important frequencies
- 🧬 **Synthesis**: Generate realistic, procedural motion
- 🤖 **ML Features**: Extract frequency-based features for training models

---

## 🔍 Motion Capture & Noise Reduction

We examined motion capture techniques:
1. **Sensor-Based** (IMUs, accelerometers)
2. **Marker-Based** (OptiTrack, Vicon)
3. **Vision-Based** (MediaPipe, OpenPose)

Using **MediaPipe**, we performed:
- **Palm Detection** → Bounding box
- **Hand Landmark Localization** → 21 (x, y, z) coordinates

### 🤯 Why Noise Is High-Frequency

- Sensor noise = quick, erratic changes → High frequency
- Smooth motion = slow variation → Low frequency

---

## 🧼 Fourier-Based Noise Filtering

We demonstrated a real-world case:

**Problem**: Sensor data from a dancer’s arm was jittery  
**Solution**:
1. Record position data over time
2. Apply **Fourier Transform** to view frequency spectrum
3. Suppress high-frequency noise
4. Apply **Inverse Fourier Transform** to reconstruct clean signal

### 📊 Result:
- Raw signal: Noisy, unstable
- After filtering: Clean motion with realistic wave-like behavior

---

## 📌 Why We Started with Fourier Series

- It builds **intuition** for periodic signal decomposition
- Real-world signals may not be periodic → motivates **Fourier Transform**
- It bridges **time-domain** and **frequency-domain** analysis—crucial for any signal-heavy domain like animation

---

## 🧠 Final Insight

> **"Laplace helps us solve equations. Fourier helps us understand and build signals."**

In animation, signals = motion, sound, emotion.  
Mastering their frequency content enables better design, denoising, compression, and control.
