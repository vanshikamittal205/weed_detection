## YOLOv8 Weed Detection Model

# Overview
This project trains a YOLOv8 model to detect weeds and crops using custom datasets. The model is trained on images and labels stored in specified directories, and the trained model can be exported for further use in applications like weed detection in agriculture.

# Requirements
Python 3.x
Jupyter Notebook
Libraries:
ultralytics (for YOLOv8)
sympy
matplotlib
numpy

# Setup
1. Install Required Libraries
Install the required Python libraries using pip:
pip install -r requirements.txt

2. Dataset Structure
   
  1. Labeled Data (labeled/)
    ● Images Directory: labeled/images/
      ○ Contains annotated images of sesame fields
      ○ Used for initial supervised learning
    ● Annotations Directory: labeled/annotations/
      ○ Corresponding annotation files for labeled images
      ○ Uses YOLOv8 annotation format
      ○ Provides ground truth for object detection training

  2. Unlabeled Data (unlabeled/)
    ● Purpose: Semi-supervised learning
    ● Contains a larger set of unannotated images of sesame fields
    ● Allows for expanding model training beyond labeled data
    ● No corresponding annotation files

  3. Test Data (test/)
    ● Images Directory: test/images/
      ○ Contains test images for model evaluation
      ○ Used for generating final predictions
    ● Annotations Directory: test/annotations/
      ○ Contains ground truth annotations for test images
      ○ Used for assessing model performance

Annotation Details
YOLOv8 Annotation Format
Annotation Structure
Each line in the annotation file typically represents: <class_id> <x_center> <y_center>
<width> <height>
● class_id: 0 (weed) or 1 (crop)
● Coordinates are normalized (0-1 scale)

3. Run the Notebook
Download the Jupyter Notebook file (sol.ipynb).
Open the notebook in Jupyter Lab or Jupyter Notebook.
Run all cells in sequence. The notebook will:
Prepare dataset paths and YAML file for YOLOv8 training.
Train the YOLOv8 model.
Evaluate the model's performance.
Save the trained model and predictions.
4. Model Training
In the notebook, you can adjust the training parameters, such as:

Number of epochs (epochs=10)
Image size (imgsz=256)
Batch size (batch=16)
Device for training (device='cpu' or cuda for GPU)
To start training, run the training cell, and the model will be trained on your dataset. The model checkpoints will be saved in the results/ directory.
