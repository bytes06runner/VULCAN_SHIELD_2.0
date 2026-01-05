🛡️ Vulcan Shield 2.0: Industrial AI PCB Inspection

Vulcan Shield 2.0 is a sophisticated, deep-learning-powered computer vision system designed for zero-defect manufacturing environments. By utilizing a custom U-Net Autoencoder architecture, the system establishes a "Neural Golden Standard" for printed circuit boards (PCBs), allowing for the instant detection and localization of structural anomalies such as burn marks, trace fractures, and component misalignments.

🚀 The Core Challenge

In high-speed electronics manufacturing, traditional rule-based computer vision often fails due to the immense complexity and texture variance of PCB traces. Vulcan Shield 2.0 bypasses traditional template matching by training a neural network to understand the topology of a perfect board. When an anomaly is introduced, the model's inability to reconstruct the defect creates a high-contrast error signature that triggers an industrial alert.

✨ Key Features

Neural Reconstruction Engine: Implements a 4-layer U-Net architecture designed specifically for 128x128 high-fidelity spatial analysis.

Dual-Metric Validation:

SSIM (Structural Similarity Index): Measures structural integrity.

MSE (Mean Squared Error): Measures pixel-level fidelity.

Diagnostic Heatmaps: Real-time generation of Jet-mapped visual analytics using power-law transformations to highlight "hot zones" of damage.

Denoising Augmented Memory: Generates a massive synthetic dataset from a single "Golden Sample" to ensure model resilience against factory vibrations and sensor jitter.

PLC Rejection Logic: Simulated Modbus/MQTT payload generation for seamless integration with factory pneumatic rejection arms.

🛠️ Technical Stack

Deep Learning: TensorFlow / Keras (U-Net Architecture)

Computer Vision: OpenCV (CLAHE, Median Filtering, Morphological Closing)

Mathematical Analytics: Scikit-Image, NumPy

Visualization: Matplotlib

📊 How It Works (The Pipeline)

CLAHE Normalization: Standardizes contrast to mitigate the effects of variable factory lighting.

Feature Bottlenecking: The U-Net encoder compresses the image into a latent space, filtering out non-essential data and focusing on "Golden" topology.

Reconstructive Inference: The decoder attempts to "repair" the input image back to perfection.

Gradient-Aware Localization: The system compares the input and output, applying median blurs and Otsu thresholding to differentiate between real defects and normal reconstruction noise.

Heatmap Overlay: A visual heatmap is superimposed on the original hardware to show engineers exactly where the structural failure occurred.

🚦 Industrial Calibration

Parameter

Value

Description

SSIM_THRESHOLD

0.85

Minimum structural similarity required to PASS

MSE_THRESHOLD

0.015

Maximum pixel-level error allowed before REJECT

EPOCHS

60

Optimized training cycles for Golden Sample memorization

IMAGE_SIZE

128x128

Standardized resolution for real-time inference

📂 Installation & Usage

Prerequisites

pip install tensorflow opencv-python matplotlib scikit-image


Quick Start

Prepare Data: Place your perfect PCB image in images/demo_good.jpg.

Target Scan: Place the PCB to be inspected in images/demo_bad.jpg.

Execution:

python vulcan_shield_v2.py


📝 Roadmap

[ ] Multi-GPU support for high-speed assembly lines.

[ ] Real-time video stream processing via RTSP.

[ ] 3D depth-map integration for height-based defect detection.

Developed for Industrial AI and Automated Quality Assurance.
