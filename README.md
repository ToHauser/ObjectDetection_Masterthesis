# PlayerDetection - FootballAI

This repository contains the final object detection configuration developed for the Master's thesis *FootballAI*. The objective is the robust detection of the object classes `player`, `referee`, and `ball` in amateur football footage.

## 📦 Repository Structure

- `config.yaml` – Training configuration for YOLOv12s (Ultralytics), including class definitions and dataset paths
- `dataset/` – Directory structure and YOLO-format annotations ([detailed explanation in `dataset/README.md`](dataset/README.md))
- `train.ipynb` – Training notebook compatible with the Ultralytics framework
- `README.md` – Repository documentation

## 🧠 Model Architecture

The detection model is based on `YOLOv12s`, fine-tuned via transfer learning using a custom drone-based dataset. The base model was pre-trained on the COCO dataset and adapted for football-specific object categories.

## 📊 Training Data Composition

- 922 images from drone footage (angled top-down perspective at ~10 meters altitude)
- 38 manually annotated penalty scene images
- 754 broadcast images from the public dataset by Skalski et al.

All annotations follow the standardized YOLO format.

🔗 [View full dataset on Roboflow](https://universe.roboflow.com/footballai-xndiy/masterthesis_dataset)
