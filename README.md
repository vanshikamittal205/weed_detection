## YOLOv8 Weed Detection Model

# Overview
This project trains a YOLOv8 model to detect weeds and crops using custom datasets. The model is trained on images and labels stored in specified directories, and the trained model can be exported for further use in applications like weed detection in agriculture.

# Requirements
Python 3.x <br>
Jupyter Notebook <br>
Libraries: <br>
ultralytics (for YOLOv8) <br>
sympy <br>
matplotlib <br>
numpy <br>

# Setup
1. Install Required Libraries <br>
Install the required Python libraries using pip: <br>
pip install -r requirements.txt <br>
 <br>
2. Dataset Structure <br>
   
  1. Labeled Data (labeled/) <br>
    ● Images Directory: labeled/images/ <br>
      ○ Contains annotated images of sesame fields <br>
      ○ Used for initial supervised learning <br>
    ● Annotations Directory: labeled/annotations/ <br>
      ○ Corresponding annotation files for labeled images <br>
      ○ Uses YOLOv8 annotation format <br>
      ○ Provides ground truth for object detection training <br>

  2. Unlabeled Data (unlabeled/) <br>
    ● Purpose: Semi-supervised learning <br>
    ● Contains a larger set of unannotated images of sesame fields <br>
    ● Allows for expanding model training beyond labeled data <br>
    ● No corresponding annotation files <br>

  3. Test Data (test/) <br>
    ● Images Directory: test/images/ <br>
      ○ Contains test images for model evaluation <br>
      ○ Used for generating final predictions <br>
    ● Annotations Directory: test/annotations/ <br>
      ○ Contains ground truth annotations for test images <br>
      ○ Used for assessing model performance <br>

Annotation Details <br>
YOLOv8 Annotation Format <br>
Annotation Structure <br>
Each line in the annotation file typically represents: <class_id> <x_center> <y_center> 
<width> <height> <br>
● class_id: 0 (weed) or 1 (crop) <br>
● Coordinates are normalized (0-1 scale) <br>

3. Run the Notebook <br>
Download the Jupyter Notebook file (final.ipynb). <br>
Open the notebook in Jupyter Lab or Jupyter Notebook. <br>
Run all cells in sequence. The notebook will: <br>
Prepare dataset paths and YAML file for YOLOv8 training. <br>
Train the YOLOv8 model. <br>
Evaluate the model's performance. <br>
Save the trained model and predictions. <br>
4. Model Training <br>
In the notebook, you can adjust the training parameters, such as: <br>

Number of epochs (epochs=10) <br>
Image size (imgsz=256) <br>
Batch size (batch=16) <br>
Device for training (device='cpu' or cuda for GPU) <br>
To start training, run the training cell, and the model will be trained on your dataset. The model checkpoints will be saved in the results/ directory. <br>
