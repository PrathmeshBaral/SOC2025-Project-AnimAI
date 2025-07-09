# SOC 2025 Project  
## AnimAI: AI-Enhanced Animation

**AnimAI** is a hands-on animation project developed as part of **Season of Codes 2025**, organized by the Web and Coding Club, IIT Bombay.  
This project blends **mathematics**, **Python programming**, and **machine learning** to bring creative animation ideas to life through structured weekly assignments.

Each week builds on foundational concepts ranging from data processing to advanced sequence modeling, applied to real-world animation and motion capture tasks.

---

## Week 1 – Data Cleaning and Visualization

In this introductory week, we explored the basics of data handling using **Pandas** and **NumPy**.

- Worked on a CSV file containing cartoon popularity and revenue statistics
- Converted string columns into numeric formats
- Handled missing values using imputation techniques
- Performed basic data visualizations to uncover trends and insights

This week built the foundation for understanding datasets before applying machine learning techniques.

---

## Week 2 – Machine Learning with CNN (MNIST)

We trained a **Convolutional Neural Network (CNN)** to classify handwritten digits from the MNIST dataset using **TensorFlow**.

- Built a simple CNN architecture from scratch
- Tuned layers, activations, and optimizers
- Achieved **99.00% accuracy** on the test set

This week introduced core machine learning principles, especially for image-based data.

---

## Week 3 – Fourier Series and Signal Denoising

Focused on applying **Fourier Series** in signal processing, especially for animation and motion data:

- Explored how complex signals can be decomposed into sinusoids
- Demonstrated denoising by removing high-frequency noise from motion data
- Reconstructed cleaner signals using inverse Fourier transforms

> _"Fourier helps us understand and build signals."_  
This assignment emphasized frequency-domain thinking—essential for motion, audio, and animation analysis.

---

## Week 4 – Filling Corrupted Frames Using Interpolation

In this week’s assignment, we tackled **noisy and incomplete pose data** using classical interpolation techniques:

- Applied **Gaussian filtering** to smooth the original 2D keypoints
- Identified missing frames and filled them using **linear** and **cubic spline** interpolation
- Compared and visualized results to evaluate effectiveness

Key takeaway: **Cubic interpolation** offers smoother results but is more computationally intensive than linear methods.

---

## Week 5 – Filling Missing Frames with LSTM

We developed an **LSTM-based neural network** to predict missing frames in a MoCap (Motion Capture) sequence.

- Used 6 surrounding frames to predict the corrupted middle frame
- Preprocessed the data with normalization
- Trained an LSTM model to learn temporal motion patterns
- Reconstructed missing frames and visualized motion recovery
- Compared original vs. reconstructed videos

This week demonstrated how sequence modeling with LSTMs can enhance motion data continuity.

---

## Week 6 – Filling Missing Frames with Bidirectional LSTM

Extended the Week 5 work using a **Bidirectional LSTM (BiLSTM)** for more powerful temporal understanding:

- Shifted joints to origin and scaled data using MinMaxScaler
- Trained a BiLSTM model to learn from both past and future context
- Reconstructed missing frames and visualized accuracy
- Compared results through:
  - `skeleton_video.mp4` (original)
  - `smoothed_skeleton_video.mp4` (reconstructed)
  - `smooth_compare.mp4` (side-by-side)

BiLSTM helped improve prediction quality by modeling full sequence context.

---

## Project Summary

**AnimAI** highlights the intersection of animation and artificial intelligence. Through structured weekly assignments, we explored:

- Data preprocessing and visualization
- Machine learning fundamentals with CNNs
- Frequency-domain signal denoising
- Classical and deep-learning-based interpolation
- Sequence modeling with LSTM and BiLSTM for motion prediction

Each assignment combined mathematical concepts with code, reflecting real-world challenges in animation technology.

---

## Author

- **Prathmesh Baral**

## Mentors

- **Harshith**
- **Yaswanth**

---

> Developed during **Season of Codes 2025**  
> Web and Coding Club – IIT Bombay
