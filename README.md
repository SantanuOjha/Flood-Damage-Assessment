# XView2 Disaster Damage Assessment and Routing

This project demonstrates a workflow for assessing building damage from satellite imagery using a U-Net model and integrating this damage information into a road network graph for damage-aware routing.

## Project Overview

The project leverages the [xView2 Challenge dataset](https://www.kaggle.com/competitions/xview2-damage-assessment) containing satellite imagery of areas before and after disasters, along with building damage annotations. The primary objectives are:

- **Semantic Segmentation:** Train a U-Net model to identify and classify building damage (no-damage, minor-damage, major-damage, destroyed).
- **Geospatial Integration:** Incorporate predicted damage information with geographic data to penalize road segments near destroyed buildings.
- **Damage-Aware Routing:** Demonstrate calculation of alternative, safer routes in disaster-affected areas using the modified road network.

## Notebook Structure

The notebook is organized into the following sections:

1. **Data Loading and Setup**  
   - Downloads the dataset using KaggleHub.  
   - Installs required libraries.

2. **Data Preprocessing**  
   - Implements a custom data generator to load and combine pre- and post-disaster images and damage masks.

3. **Model Definition and Training**  
   - Defines and trains a U-Net model with a ResNet34 backbone for semantic segmentation of building damage.

4. **Prediction Visualization**  
   - Visualizes model predictions on sample images.

5. **Geospatial Integration**  
   - Retrieves road network data using OSMnx.  
   - Converts pixel coordinates to geographic coordinates.  
   - Updates the road network graph with damage information.

6. **Damage-Aware Routing**  
   - Calculates shortest paths on both the original and damage-penalized road networks.

7. **Flood Detection (Experimental)**  
   - Detects potential flooded paths in post-disaster images using image processing techniques.

## How to Run

1. **Open in Colab**  
   Open the notebook in [Google Colab](https://colab.research.google.com/).

2. **Install Dependencies**  
   Run the installation cell for required libraries:
   - `segmentation-models`
   - `Pillow`
   - `scikit-image`
   - `tensorflow`
   - `kagglehub`
   - `osmnx`
   - `shapely`
   - `networkx`
   - `opencv-python`
   - `gdown`

3. **Download Data**  
   Use KaggleHub to download the xView2 dataset.

4. **Execute Notebook Cells**  
   Sequentially run the remaining cells to preprocess data, train the model, and perform the damage assessment and routing analysis.

## Requirements

- Python 3.7+
- TensorFlow 2.x
- Keras
- Segmentation Models
- KaggleHub
- Pillow
- Scikit-image
- OSMnx
- Shapely
- NetworkX
- OpenCV-Python
- Gdown

> All dependencies are installed within the notebook.

## Dataset

- **Source:** [xView2 Challenge dataset](https://www.kaggle.com/competitions/xview2-damage-assessment) on Kaggle.
- Contains satellite imagery and building damage annotations (pre- and post-disaster).

## Model

- **Architecture:** U-Net with ResNet34 encoder.
- **Pre-training:** Encoder weights pre-trained on ImageNet.
- **Task:** Fine-tuned on xView2 for semantic segmentation of building damage.

## Future Work

- Improve model performance with hyperparameter tuning, data augmentation, or alternative architectures.
- Enhance flood detection and integrate with routing.
- Implement a user interface for interactive routing.
- Perform thorough evaluation of the damage-aware routing strategy.

---

**License:** See repository for license information.

**Contact:** For questions or contributions, please open an issue or submit a pull request.
