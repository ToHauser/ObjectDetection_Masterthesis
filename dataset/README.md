# Dataset Structure and Processing Workflow

## Overview
This repository contains the dataset preparation workflow for the FootballAI object detection project. The dataset is composed of **50% own annotated data** and **50% broadcast data**, which are combined and processed into separate sets for original images and tile-based crops. Data augmentation is performed using **Roboflow**.

---

## Folder Structure

### `raw_training_images`
- Contains all raw training images.
- Composition: **50% own annotated data** and **50% broadcast data**.
- For clarity of origin, two additional folders are maintained:
  - `raw_training_images/own_data/` — stores the 50% own annotated data. [Custome Drone Dataset ](https://universe.roboflow.com/footballai-xndiy/drohnenvideos/dataset/6)
  - `raw_training_images/broadcast_data/` — stores the 50% broadcast data. [Skalski Broadcast Dataset](https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc/dataset/1)

- These two folders are merged into:
  - `raw_training_images/images/` — used for further processing.

---

### `train_tiles`
- Created by `pipeline.py`.
- Contains **50% of the images** from `raw_training_images/images`.
- Used for creating **tile splits** from the selected images.

---

### `roboflow_images`
Contains the processed images ready for Roboflow augmentation, split into two categories:

#### `roboflow_images/tiles_resized/`
- Stores the **selected tile images**.
- Each tile contains at least one object.
- Matches the Roboflow project folder:
  [Tile Augmentation Project](https://app.roboflow.com/footballai-xndiy/1-2-tileaugmentation/1)

#### `roboflow_images/original_resized/`
- Stores the **selected original full-frame images**.
- Matches the Roboflow project folder:
  [Original Augmentation Project](https://app.roboflow.com/footballai-xndiy/2-2-originalaugmentation/1)

---

## Image Counts
- **Full-frame images:** 687  
- **Tile-frame images:** 475

---

## Augmentation
For both sets of images (**full-frame** and **tile-frame**), augmentations are carried out using Roboflow to increase variability and reduce overfitting.

---
