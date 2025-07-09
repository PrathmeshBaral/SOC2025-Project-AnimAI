# Week 6 Assignment – Filling Missing Frames in MoCap Data Using Bidirectional LSTM

This assignment extends the previous work on frame reconstruction by utilizing a **Bidirectional LSTM (BiLSTM)** network to predict and fill missing frames in Motion Capture (MoCap) sequences. The goal is to explore how bidirectional temporal modeling can enhance the quality of frame interpolation.

## Objective

To predict missing frames in MoCap data through a BiLSTM network. This helps the model better understand motion flow from both directions.

## Workflow Summary

1. **Data Loading**
   - Used the same MoCap dataset as in Week 5.
   - Selected: Subject S7, Action "Walking 1", Camera 0.

2. **Missing Frame Identification**
   - Identified corrupted or missing frames.

3. **Preprocessing**
   - Shifted each frame so that the center joint is at the origin to maintain spatial consistency.
   - Applied `MinMaxScaler` to normalize joint coordinate values.
   - Flattened each frame to shape `(34,)` (17 joints × 2 coordinates).

4. **Dataset Creation**
   - Used sequences of known frames to generate training input and output pairs.
   - Window size was set to 1, but can be modified based on the task.
   - Inputs shape: `(window_size, 34)`, Outputs shape: `(34,)`.

5. **Model Architecture**
   - Built a BiLSTM-based model:
     - Two Bidirectional LSTM layers
     - Followed by dense layers for regression
     - Used ReLU activations and linear output
   - Dropout was not used due to the small and specific dataset.

6. **Training**
   - Optimizer: Adam with learning rate `1e-3`
   - Loss: Mean Squared Error (MSE)
   - Early stopping used to avoid overfitting

7. **Reconstruction and Evaluation**
   - Reconstructed missing frames using the trained model.
   - Calculated reconstruction error for each frame.
   - Plotted the best and worst predicted frames for visual inspection.

8. **Visualization**
   - `skeleton_video.mp4`: Original MoCap with missing frames
   - `smoothed_skeleton_video.mp4`: Reconstructed output using BiLSTM
   - `smooth_compare.mp4`: Side-by-side comparison of original vs. reconstructed video

## Summary

This assignment demonstrates how **Bidirectional LSTM** can leverage both past and future context to improve frame reconstruction in MoCap data. The model was able to smoothly interpolate missing frames, and visual and quantitative evaluations showed meaningful improvements over unprocessed sequences.
