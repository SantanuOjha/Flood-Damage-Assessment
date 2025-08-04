XView2 Disaster Damage Assessment and Routing
This notebook demonstrates a workflow for assessing building damage from satellite imagery using a U-Net model and then integrating this damage information into a road network graph to perform damage-aware routing.

Project Overview
The project uses the xView2 Challenge dataset, which contains satellite imagery of areas before and after various disasters, along with building damage annotations. The goal is to:

Train a semantic segmentation model to identify and classify building damage (no-damage, minor-damage, major-damage, destroyed).
Integrate the predicted damage information with geographic data to penalize road segments near destroyed buildings.
Demonstrate how this damage information can be used to calculate alternative, safer routes in a disaster-affected area.
Notebook Contents
The notebook is structured as follows:

Data Loading and Setup: Downloads the dataset using KaggleHub and installs necessary libraries.
Data Preprocessing: Implements a custom data generator to load and combine pre- and post-disaster images and their corresponding damage masks.
Model Definition and Training: Defines and trains a U-Net model with a ResNet34 backbone for semantic segmentation of building damage.
Prediction Visualization: Visualizes the model's predictions on sample images.
Geospatial Integration: Defines functions to retrieve road network data using OSMnx, convert pixel coordinates to geographic coordinates, and update the road network graph with damage information.
Damage-Aware Routing: Demonstrates calculating shortest paths on both the original and damage-penalized road networks.
Flood Detection (Experimental): Includes an experimental section for detecting potential flooded paths in post-disaster images using image processing techniques.
How to Run
Open in Colab: Open this notebook in Google Colab.
Install Dependencies: Run the cell that installs the required libraries (segmentation-models, Pillow, scikit-image, tensorflow, kagglehub, osmnx, shapely, networkx, opencv-python, gdown).
Download Data: Run the cell that downloads the dataset from KaggleHub.
Execute Cells: Run the remaining cells sequentially to preprocess data, train the model, and perform the damage assessment and routing analysis.
Requirements
Python 3.7+
TensorFlow 2.x
Keras
Segmentation Models
KaggleHub
Pillow
Scikit-image
OSMnx
Shapely
NetworkX
OpenCV-Python
Gdown
These dependencies are installed within the notebook.

Dataset
The dataset used is the xView2 Challenge dataset available on Kaggle.

Model
The model used is a U-Net with a ResNet34 encoder, pre-trained on ImageNet (encoder weights). It is fine-tuned on the xView2 dataset for semantic segmentation of building damage.

Future Work
Improve model performance with hyperparameter tuning, data augmentation, or different architectures.
Enhance the flood detection and integration with routing.
Implement a user interface for interactive routing.
Perform a more thorough evaluation of the damage-aware routing strategy.
