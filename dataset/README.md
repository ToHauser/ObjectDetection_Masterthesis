# Dataset Structure and Processing Workflow

## Overview
This repository contains the dataset preparation workflow for the FootballAI object detection project.  
The dataset consists of approximately **50% own annotated drone footage** and **50% broadcast footage** from the publicly available dataset by [Skalski](https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc/dataset/1).  
An additional **38 penalty-scene images** are included to improve detection performance in goal-related scenarios.  
Data is processed into separate sets for **original full-frame images** and **tile-based crops**.  
Data augmentation is performed using **Roboflow** and custom scripts.

---

## Folder Structure

### `raw_training_images`
- Contains all raw training images.
- Composition:  
  - `raw_training_images/own_data/` — [Custom Drone Dataset](https://universe.roboflow.com/footballai-xndiy/drohnenvideos/dataset/6)  
  - `raw_training_images/broadcast_data/` — [Skalski Broadcast Dataset](https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc/dataset/1)
- Merged into:  
  - `raw_training_images/images/` — used for further processing.

---

### `train_tiles`
- Created by `pipeline.py`.
- Contains **45% of the training images** from `raw_training_images/images` that are split into tiles.
- Only tiles containing at least one ball instance are retained.

---

### `roboflow_images`
Contains the processed images ready for augmentation.

#### `roboflow_images/tiles_resized/`
- Selected **tile images** (at least one ball object per tile). These images serve as input for the augmentation on Roboflow:
  [Tile Augmentation Dataset (augmented ×3)](https://universe.roboflow.com/footballai-xndiy/1-2-tileaugmentation/dataset/1)

#### `roboflow_images/original_resized/`
- Selected **original full-frame images**. These images serve as input for the augmentation on Roboflow:
  [Full-Frame Augmentation Dataset (augmented ×3)](https://universe.roboflow.com/footballai-xndiy/2-2-originalaugmentation/dataset/1)

#### `01_Penalty_Images/`
- Penalty-scene images (augmented ×8 using custom scripts due to Roboflow limitations).
- Dataset available in this repository folder: [Penalty Images Ordner](https://github.com/ToHauser/ObjectDetection_Masterthesis/tree/main/dataset/01_Penalty_Images)

---

## Image Counts
- **Full-frame images (pre-augmentation):** 687  
- **Tile images (pre-augmentation):** 475  
- **Penalty images (pre-augmentation):** 38  

---

## Augmentation
Augmentation is applied separately to each image category to increase variability and reduce overfitting.  
- **Tile images:** ×3 augmentation ([link](https://universe.roboflow.com/footballai-xndiy/1-2-tileaugmentation/dataset/1))  
- **Full-frame images:** ×3 augmentation ([link](https://universe.roboflow.com/footballai-xndiy/2-2-originalaugmentation/dataset/1))  
- **Penalty images:** ×8 augmentation (local script, see `01_Penalty_Images/` folder)  

**Final dataset size:**  
After preprocessing and augmentation, the training set comprised:  
- 1,425 augmented tile images  
- 2,061 augmented full-frame images  
- 208 augmented penalty-scene images  

In total, the augmented training set contains **3,694 images**. Validation and test sets remain unaugmented.

---
