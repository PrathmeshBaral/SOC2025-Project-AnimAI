# Week 5 Assignment – Filling Missing Frames in MoCap Data Using LSTM

This project focuses on restoring missing or corrupted frames in Motion Capture (MoCap) data using a deep learning model. The task simulates real-world data corruption and explores how sequential models can learn to reconstruct missing information from temporal context.

## Objective

The goal is to predict a missing middle frame from a sequence of 7 consecutive frames using the 3 frames before and 3 after it. This is framed as a supervised regression problem, with an LSTM-based neural network trained to learn motion patterns across time.

## Dataset

- Source: Human3.6M-like MoCap data
- Selected sequence: Subject **S7**, Action **Walking 1**, Camera **0**
- Shape: `(3637, 17, 2)` → 3637 frames, 17 joints per frame, (x, y) coordinates

## Approach

1. **Data Preprocessing**:  
   - Flattened frames from `(17, 2)` to `(34,)`  
   - Applied MinMax normalization  
   - Identified missing frames

2. **Training Data Generation**:  
   - Used a sliding window of 7 known frames  
   - Input: 6 surrounding frames  
   - Target: middle (4th) frame

3. **Model Architecture**:  
   - Two stacked LSTM layers to learn temporal patterns  
   - Followed by dense layers for regression  
   - Trained using MSE loss with Adam optimizer

4. **Prediction and Reconstruction**:  
   - Missing frames predicted using the trained model  
   - Results inserted back into the original sequence

5. **Evaluation**:  
   - Calculated mean squared error for each reconstructed frame  
   - Identified best and worst predictions for visualization

6. **Visualization**:  
   - Generated videos to compare original and reconstructed motion

## Output Videos

- `Week5_skeleton_video.mp4` — Original with missing frames  
- `Week5_smoothed_skeleton_video.mp4` — After reconstruction  
- `Week5_smooth_compare.mp4` — Side-by-side comparison

## Summary

This assignment demonstrates how LSTM networks can effectively reconstruct corrupted sequential data by learning patterns in motion. It highlights the potential of deep learning in noise reduction, data recovery, and motion interpolation tasks.
