# Model Details — Bariq

## Datasets
- **AIROGS-light-V2** (clinical): ~9,000 fundus images, 70/15/15 split
- **Brazil Glaucoma (BrG)** (mobile): 1,999 images from 1,000 volunteers, 
  80/10/10 split

## Models

### Medical_ResNet50
- Backbone: ResNet50 (ImageNet pretrained), PyTorch
- 3-stage transfer learning (head-only → full unfreeze → fine-tune)
- Test AUC: 0.9603 | Test Accuracy: 89.35%

### Mobile_ResNet50
- Backbone: ResNet50 (ImageNet pretrained), PyTorch
- 2-stage transfer learning
- Test AUC: 0.9716 | Test Accuracy: 94.03%

### Mobile_MobileNetV2
- Backbone: MobileNetV2 (ImageNet pretrained)
- Test AUC: 0.9622 | Test Accuracy: 90.55%

### Mobile_VGG16
- Backbone: VGG16 (ImageNet pretrained)
- Test AUC: 0.9592 | Test Accuracy: 89.05%

## Final Ensemble
- Weighted average of all 4 models
- **AUC: 0.9654** | **Accuracy: 94.03%**
- Precision: 0.97 | Recall: 0.91 | F1-score: 0.94
