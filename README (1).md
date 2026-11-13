# Adaptive Traffic Control System Using YOLOv8 and CNN

**Undergraduate Capstone Project | February–April 2024**  
**B.E. in Computer Engineering — Paschimanchal Campus, Institute of Engineering, Tribhuvan University**

## Overview

This project explores a computer-vision-based approach to adaptive traffic signal control. The system uses a trained **YOLOv8 object detection model** to identify vehicles in road-traffic video frames and estimate traffic density. These estimates inform a **CNN-based approach to traffic-signal timing**, with the overall workflow evaluated in simulation.

The motivation is to investigate how visual information about changing traffic conditions can support signal-timing decisions, rather than relying exclusively on fixed-duration traffic lights. This was an undergraduate team capstone project and a practical exploration of combining object detection, machine learning, and simulated traffic control.

## Project Objectives

- Collect and preprocess road-traffic video data for vehicle detection.
- Train a YOLOv8 detector to identify vehicles in video frames.
- Derive traffic-density estimates from detected vehicles.
- Explore adaptive signal timing using a CNN-based approach informed by the estimated traffic conditions.
- Evaluate the proposed workflow in a simulated traffic-control setting.

## System Workflow

```text
Road-traffic video
       |
       v
Frame extraction and preprocessing
       |
       v
YOLOv8 vehicle detection
       |
       v
Vehicle-based traffic-density estimation
       |
       v
CNN-based adaptive signal-timing approach
       |
       v
Traffic-control simulation and evaluation
```

### 1. Traffic Video Preparation

Road-traffic footage was collected and prepared as input to the vehicle-detection stage. Preprocessing organized the visual data for model training and frame-level analysis.

### 2. Vehicle Detection with YOLOv8

A YOLOv8 object detection model was trained to identify vehicles in traffic imagery. Its predictions were used to estimate traffic density from video frames. This stage provides the visual input for the downstream signal-timing approach.

### 3. Adaptive Traffic-Signal Timing

A CNN-based approach was developed to inform traffic-signal timing using the vehicle-density estimates. The goal was to explore signal control that responds to observed traffic conditions.

### 4. Simulation-Based Evaluation

The proposed workflow was evaluated through simulation. This is a proof-of-concept evaluation; it should not be interpreted as evidence of deployment at a physical intersection or as a quantified reduction in congestion without additional measurements.

## Repository Contents

The repository currently includes the following top-level items:

```text
post-final-year-project/
├── model_training/
│   └── results/
├── simulation/
├── project idea.pdf
├── .gitignore
└── README.md
```

- [`model_training/results/`](model_training/results/) — model-training results directory.
- [`simulation/`](simulation/) — simulation-related project files.
- [`project idea.pdf`](project%20idea.pdf) — original project concept document.

> **Reproducibility note:** This README describes the project workflow, but does not claim a verified one-command setup. Exact dependencies, dataset access instructions, model checkpoints, and execution commands should be added after checking the available scripts and files in the repository.

## Methods and Evaluation

The project has two distinct technical components: **vehicle detection/traffic-density estimation** and **traffic-signal timing**. The simulation explores their integration.

For a more reproducible technical report, the following details should be documented when available:

| Component | Information to document |
| --- | --- |
| Dataset | Footage source, size, annotation procedure, and train/validation/test split |
| YOLOv8 training | Model variant, initialization, image size, epochs, and hyperparameters |
| Detection evaluation | Precision, recall, and mAP on held-out data |
| Density estimation | Counting or aggregation rule, region of interest, and error analysis |
| CNN-based timing | Input features, model architecture, target/output, and training procedure |
| Traffic simulation | Simulator, traffic scenarios, baseline timing strategy, and evaluation metrics |

**Reported results:** Numerical accuracy, mAP, waiting-time, or congestion-reduction figures are intentionally omitted here because they have not been verified against the repository artifacts.

## Limitations

- Simulation-based results do not establish performance in real-world traffic intersections.
- Detection errors, occlusion, lighting, and camera viewpoint may affect density estimates and downstream signal decisions.
- A fair comparison with fixed-time control requires matched traffic scenarios, evaluation metrics, and documented experimental settings.
- Further documentation is needed to make training and simulation fully reproducible from this repository alone.

## Future Improvements

- Document the dataset, model configuration, experimental environment, and exact run commands.
- Report detection metrics and simulation metrics against a fixed-timing baseline.
- Test robustness across different traffic densities, camera conditions, and road layouts.
- Package model training, inference, and simulation into a reproducible workflow.

## Project Context

This work was completed as an **undergraduate capstone project (February–April 2024)**. It provided hands-on experience in preparing visual data, training an object detection model, connecting machine-learning outputs to a downstream decision process, and evaluating an applied system in simulation.

**Repository:** https://github.com/sameen-wq/post-final-year-project
