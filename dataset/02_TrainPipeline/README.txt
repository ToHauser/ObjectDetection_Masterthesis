The Structure looks as followed:

Folder: raw_training_images contains the images of 50% own annotated data / 50% broadcast data
Note: For clearity of origin, two additional folders are created where the original 50% own data is stored and another where only the 50% broadcast data is stored. Those two Folders are being merged into the raw_training_images/images Folder.

Folder: train_tiles is being created by the pipeline.py script. There 50% of the images in raw_training_images/images are stored for further processing to create the tile splits on those images.

Folder: roboflow_images contains two seperate folder that are being produced by the pipeline.py script. One Folder Stores the Tile Frames, one folder stores the other 50% of original images.

Folder: roboflow_images/tiles_resized/ stores the selected Tile Images, where each image contains at least one object. This Folder equals the Tiles Project Folder on Roboflow where the augmentation is being carried out: https://app.roboflow.com/footballai-xndiy/1-2-tileaugmentation/1

Folder: roboflow_images/original_resized/ stores the selected original Images. This Folder equals the OriginalAugmentation Project Folder on Roboflow where the augmentation is being carried out: https://app.roboflow.com/footballai-xndiy/2-2-originalaugmentation/1

In the end 687 full-frame images are being produced; 475 Tile-Frame images are being produced.
For each set of images a Augmentation is being carried out on roboflow.

