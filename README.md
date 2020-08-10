# Foreign-Object-Detection-in-X-Rays
This repository concludes our work on a foreign object detector in X-Ray images as students in TAU, as part of a course in Deep Learning, and as participants in the competition: https://jfhealthcare.github.io/object-CXR/.

The goal of the competition was to create an object detector, that could be used to ease the process of X-Ray analysis.

## create_predictions_dataset.ipynb
This notebook is used to create a bunch of pickle files, that each contain a dataframe of about 1,000 images.
The notebook does the following:
  - it loads data from the competition
  - it loads the model of ChexNet, together with the weights, from this wonderfull repository: https://github.com/brucechou1983/CheXNet-Keras
  - the notebook adds augmentations such as minor rotations and  horizontal flipls
  - it feeds the images into the DenseNet, and extracts features from variuous layers
  - it saves the pickles
  
## dense_model.ipynb
This notebook finetunes the DenseNet model that was loaded, based on the dataset that was created in the above notebook.

## resnet.ipynb
This note book finetunes an imagenet resnet, based on the dataset that was created in the aforementioned notebook.

## grad_cam.ipynb
This notebook uses code from the repository: https://github.com/eclique/keras-gradcam, in order to perform GradCAM analysis on the output from the DenseNet model.

## network trials.xlsx
This excel files contains documentation regarding several trials regarding the training of the densenet model. 
