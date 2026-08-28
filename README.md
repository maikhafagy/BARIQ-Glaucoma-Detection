# Project Architecture — Bariq

## Overview
Bariq is a deep learning system for automated glaucoma detection from retinal 
fundus images, supporting two input sources: clinical medical images and 
mobile camera images.

## Pipeline
1. **Image Input** — clinical fundus camera or mobile phone camera
2. **Preprocessing** (separate pipeline per domain):
   - Duplicate detection (MD5 hashing)
   - Image quality gating (blur, brightness checks)
   - Smart crop / region-of-interest detection (mobile only)
   - Color balance correction (mobile only)
   - LAB-CLAHE contrast enhancement
   - Circular masking to isolate the retinal area
   - Resize to 224×224, normalization
3. **Model Inference** — 4-model ensemble (weighted average):
   - Medical_ResNet50
   - Mobile_ResNet50
   - Mobile_MobileNetV2
   - Mobile_VGG16
4. **Explainability** — Grad-CAM heatmap generation on the primary model
5. **Clinical Risk Scoring** — combines model output (70%) with patient risk 
   factors such as age, IOP, diabetes, and family history (30%)
6. **API Layer** — FastAPI backend serving predictions to the Flutter mobile app

## Deployment
- Backend: FastAPI + Uvicorn
- Models exported to ONNX for lighter deployment
- Frontend: Flutter mobile application
