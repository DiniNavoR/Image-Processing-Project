Swimming Video Image Processing Assignment
Overview

This project involves the application of image processing techniques to analyze swimming videos. The main goal is to enhance, segment, and track swimmers in video frames, followed by qualitative and quantitative evaluation of the results.

Three high-definition swimming videos were used from YouTube:

Swimming Finals Women's 400m Individual Medley – 29th SEA Games 2017
Video Link

Resolution: 1920 × 1080
Duration: 2:47 – 2:56
Frame Rate: 30 FPS

Summer McIntosh breaks own world record – 400m IM Canadian Swim Trials, CBC Sports
Video Link

Resolution: 1920 × 1080
Duration: 4:01 – 4:15
Frame Rate: 30 FPS

Swimming Women's 4×100m Medley Relay Final – Tokyo 2020 Replays
Video Link

Resolution: 1920 × 1080
Duration: 3:58 – 4:06
Frame Rate: 30 FPS

Since the original videos were long, 15-second clips were extracted from each video for processing.

Processing Pipeline
1. Frame Extraction

All videos were converted into frames at 30 FPS.

Frames were first converted to grayscale to reduce computational complexity and simplify processing.

2. Image Enhancement

The enhancement stage improves the quality of frames before segmentation. The enhancement flowchart is as follows:

Input Frame
     ↓
Resize
     ↓
Gaussian Blur
     ↓
Histogram Equalization
     ↓
Sharpening Filter
     ↓
Enhanced Frame

Enhancement Techniques Used:

Resize: Maintain uniform resolution for processing.

Gaussian Blur: Remove high-frequency noise caused by water bubbles and reflections.

Histogram Equalization: Improve contrast between swimmer and background.

Sharpening Filter: Enhance edges for better segmentation.

3. Segmentation Pipeline

After enhancement, swimmer regions are isolated using color-based segmentation. The pipeline is:

Enhanced Frame
       ↓
HSV Color Conversion
       ↓
Color Thresholding
       ↓
Mask Inversion
       ↓
Morphological Filtering
       ↓
Swimmer Segmentation

Segmentation Techniques Used:

HSV Color Conversion: Easier identification of swimmer colors against water.

Color Thresholding: Extract swimmer region.

Mask Inversion: Highlight swimmer in the binary mask.

Morphological Filtering: Remove small noise areas and smooth segmented region.

4. Experimental Dataset
Match	Resolution	FPS	Frames Tested
Match 1	1920 × 1080	30	294
Match 2	1920 × 1080	30	404
Match 3	1920 × 1080	30	251
Results
1. Qualitative Evaluation

Objective: Visual analysis of the effectiveness of enhancement and segmentation.

Observations:

Enhanced frames showed better contrast between swimmers and water.

Edges of swimmers became more visible.

Noise caused by water bubbles and reflections was reduced.

Segmentation Results:
Original frames were processed through the segmentation pipeline to produce binary masks and isolate swimmers:

Original Frame → Enhanced Frame → Binary Mask → Segmented Swimmer
2. Quantitative Evaluation

Objective: Measure computational performance and consistency.

Metrics:

Processing Time per Frame: Measures computational cost.

Tracking Accuracy: Evaluates consistency of swimmer detection.

Detection Consistency: Measures stability of segmentation across frames.

Presentation: Results can be displayed using tables, graphs, and comparative figures.

Notes

The project demonstrates the practical application of image enhancement, color-based segmentation, and basic tracking techniques in sports video analysis.

The methods can be extended to real-time swimmer tracking or motion analysis for coaching and performance evaluation.
