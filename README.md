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
  

### Training

* Describe the training:
  * How you trained: software and hardware.
  * How did training take.
  * Training curves (loss vs epoch for test/train).
  * How did you decide to stop training.
  * Any difficulties? How did you resolve them?

### Performance Comparison

* Clearly define the key performance metric(s).
* Show/compare results in one table.
* Show one (or few) visualization(s) of results, for example ROC curves.

### Conclusions

* State any conclusions you can infer from your work. Example: LSTM work better than GRU.

### Future Work

* What would be the next thing that you would try.
* What are some other studies that can be done starting from here.

## How to reproduce results

* In this section, provide instructions at least one of the following:
   * Reproduce your results fully, including training.
   * Apply this package to other data. For example, how to use the model you trained.
   * Use this package to perform their own study.
* Also describe what resources to use for this package, if appropirate. For example, point them to Collab and TPUs.

### Overview of files in repository

* Describe the directory structure, if any.
* List all relavent files and describe their role in the package.
* An example:
  * utils.py: various functions that are used in cleaning and visualizing data.
  * preprocess.ipynb: Takes input data in CSV and writes out data frame after cleanup.
  * visualization.ipynb: Creates various visualizations of the data.
  * models.py: Contains functions that build the various models.
  * training-model-1.ipynb: Trains the first model and saves model during training.
  * training-model-2.ipynb: Trains the second model and saves model during training.
  * training-model-3.ipynb: Trains the third model and saves model during training.
  * performance.ipynb: loads multiple trained models and compares results.
  * inference.ipynb: loads a trained model and applies it to test data to create kaggle submission.

* Note that all of these notebooks should contain enough text for someone to understand what is happening.

### Software Setup
* List all of the required packages.
* If not standard, provide or point to instruction for installing the packages.
* Describe how to install your package.

### Data

* Point to where they can download the data.
* Lead them through preprocessing steps, if necessary.

### Training

* Describe how to train the model

#### Performance Evaluation

* Describe how to run the performance evaluation.


## Citations

* Provide any references.







