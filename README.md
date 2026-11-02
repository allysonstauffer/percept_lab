# PerceptLab
### Evaluating Computer Vision Reliability for Autonomous Vehicle Perception

**Status:** In Development  
**Focus:** Computer Vision · Machine Learning · Model Evaluation · Autonomous Vehicles

## Overview

PerceptLab is an independent computer vision project focused on evaluating and improving the reliability of pretrained perception models for autonomous driving.

The project investigates how accurately a semantic segmentation model identifies drivable areas in road imagery, how its performance changes under degraded visual conditions, and whether targeted improvements can increase reliability.

Rather than training a model from scratch, PerceptLab focuses on understanding the end-to-end machine learning engineering workflow: model inference, evaluation, experimentation, improvement, and deployment.

## Research Question

**How reliably can a pretrained computer vision model identify drivable areas under changing visual conditions, and what techniques can improve its performance?**

## Project Goals

1. Run a pretrained semantic segmentation model on labeled road imagery.
2. Develop a reproducible framework for evaluating model predictions.
3. Measure model performance using segmentation metrics.
4. Test model robustness under blur, low lighting, noise, and image compression.
5. Experiment with preprocessing or model improvements and compare results against the baseline.
6. Deploy model inference through an API and explore AWS infrastructure.

## Technical Stack

| Category | Technologies |
|---|---|
| Language | Python |
| Machine Learning | PyTorch |
| Computer Vision | OpenCV |
| Data Processing | NumPy, Pandas |
| Evaluation | IoU, Precision, Recall |
| Visualization | Matplotlib |
| API Development | FastAPI |
| Deployment (Planned) | Docker, AWS S3, SageMaker |
| Version Control | Git, GitHub |

## Dataset and Model

**Dataset:** To be finalized. BDD100K is an initial candidate because it provides road-scene imagery and segmentation annotations.

**Model:** A pretrained semantic segmentation model with output classes compatible with the selected dataset's drivable-area labels.

Model selection will prioritize reproducible inference, available pretrained weights, and compatibility with ground-truth annotations.

## Methodology

### Phase 1 — Baseline Model (November 2–8)

- Select a labeled road-scene dataset.
- Set up Python, PyTorch, and OpenCV.
- Load a pretrained segmentation model.
- Run inference on a small set of images.
- Visualize predicted segmentation masks against ground-truth labels.

**Deliverable:** Working baseline inference pipeline and sample predictions.

### Phase 2 — Evaluation Framework (November 9–15)

Implement quantitative metrics to evaluate model performance.

- Intersection-over-Union (IoU)
- Precision and recall
- False-negative rate
- Inference latency

Generate reproducible evaluation reports and identify examples where the model performs poorly.

**Deliverable:** Baseline evaluation results and documented failure cases.

### Phase 3 — Robustness Testing (November 16–22)

Apply controlled transformations to test model reliability under changing visual conditions.

- Gaussian blur
- Reduced brightness
- Image noise
- JPEG compression

Compare predictions against the original ground-truth masks and measure performance degradation.

**Deliverable:** Robustness comparison results and visualizations.

### Phase 4 — Model Improvement (November 23–30)

Investigate techniques for improving model performance.

Potential approaches include:

- Image preprocessing
- Contrast enhancement
- Input normalization adjustments
- Fine-tuning, if feasible

Compare the improved approach against the original baseline on held-out evaluation data.

**Deliverable:** Before-and-after performance comparison and documented findings.

### Phase 5 — Deployment (Planned: December)

Wrap model inference in a deployable application.

- Build a FastAPI inference endpoint.
- Containerize the application with Docker.
- Explore AWS S3 for dataset and artifact storage.
- Investigate SageMaker for managed ML inference.
- Evaluate inference latency and deployment tradeoffs.

**Deliverable:** Functional inference API and documented deployment architecture.

## Evaluation Strategy

The primary evaluation metric will be **Intersection-over-Union (IoU)**, which measures overlap between predicted and ground-truth drivable-area masks.

Additional metrics will help identify missed drivable regions, incorrectly predicted regions, computational costs, and performance degradation under visual transformations.

Experiments will use consistent evaluation data and documented configurations to support reproducibility.

## Expected Outcomes

By the end of the project, PerceptLab aims to demonstrate:

- A functional pretrained computer vision inference pipeline.
- A reproducible model evaluation framework.
- Quantitative analysis of perception reliability.
- Controlled robustness experiments.
- Evidence-based model improvement.
- A deployable inference API.

## Future Extensions

- Evaluate obstacle detection models.
- Compare multiple pretrained architectures.
- Explore synthetic training data and domain adaptation.
- Investigate how perception errors affect navigation decisions.
- Extend evaluation to real-time video and edge devices.

## Project Motivation

PerceptLab builds on my previous work in AI model evaluation, geospatial navigation, and image-related data validation.

My goal is to develop practical experience in applied machine learning engineering by understanding not only how to run pretrained models, but also how to evaluate their reliability, investigate failures, improve performance, and deploy them in real-world systems.
