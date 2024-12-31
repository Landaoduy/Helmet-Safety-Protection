# Helmet-Safety-Protection

## Overview

* This project implements an automated helmet detection system using YOLOv10 to enhance workplace safety in construction areas. The system can identify multiple objects including persons, heads, and safety helmets in images, making it useful for monitoring personal protective equipment (PPE) compliance.

### Features

* Real-time detection of safety helmets
* Multiple object detection capabilities:
  * Person detection
  * Head detection
  * Helmet detection
* High accuracy object detection using YOLOv10
* Configurable confidence threshold for detections
* Support for various image sizes and batch processing

### Technical Details

* **Model Architecture**:
  * Base Model: YOLOv10
  * Input Image Size: 320x320 pixels
  * Framework: PyTorch with Ultralytics implementation

* **Training Configuration**:
  * Epochs: 50
  * Batch size: 64
  * Image size: 320x320
  * Dataset: Safety Helmet Dataset
    
* **Installation**:
  ```sh
  # Clone YOLOv10 repository
  git clone https://github.com/THU-MIG/yolov10.git

  # Install requirements
  cd yolov10
  pip install -r requirements.txt
  pip install -e .
  ```
* **Dataset**:
  * The project uses a custom Safety Helmet Dataset containing annotated images of construction workers with and without helmets.
    
  * The dataset is organized with the following structure:
    * train
    * test
    * data.yaml
      
### Training Process
```sh
# Initialize model
model = YOLOv10('yolov10n.pt')

# Training configuration
model.train(
    data='path/to/data.yaml',
    epochs=50,
    batch=64,
    imgsz=320,
    amp=True
)
```

### Model Evaluation

* The model performs validation on a separate test set to ensure reliable performance metrics. Evaluation can be run using:
  ```sh
  model.val(data='path/to/data.yaml', imgsz=320, split='test')
  ```
* **Images**:
  ![helmet_output](https://github.com/user-attachments/assets/08ff777d-6859-4046-8c71-86eb5127d8b9)

### Inference
```sh
# Load trained model
model = YOLOv10('path/to/best.pt')

# Run inference
results = model.predict(
    source='path/to/image.jpg',
    imgsz=320,
    conf=0.3  # Confidence threshold
)
```

### Performance Metrics

* Processing Speed: ~85ms per image (including pre/post-processing)
  * Preprocessing: 1.7ms
  * Inference: 82.7ms
  * Postprocessing: 1.0ms


