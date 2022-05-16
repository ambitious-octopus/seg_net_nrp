# Prednet Segmentation

## Setup

- Create a and load new venv: 
  ```bash
  python -m venv venv
  source venv/bin/activate
  ```
- Install pytorch and additional packages:
  ```bash
  pip install wheel
  pip install -r requirements.txt
  ```

## Run setup

- Activate venv: `source venv/bin/activate`
- Run: `python ros_img_segmentation.py`

## ros\_img\_segmentation.py

The node subscribes to a camera image topic, here `/camera/camera/image`. It registers a series of image topics to output segmented images. An individual topic is used for each identified object, under `/prednet_segmentation/{item_name}/image`. In `test_ros.py`, we define three objects to identify. At this time, it's outputting noise and should only be used to setup the interface.

## Segmentable meshes

At the moment, the model can segment the following meshes from the YCB dataset:

- a\_marbles
- apple
- banana
- shelf
- adjustable\_wrench
- flat\_screwdriver
- mug
- phillips\_screwdriver
- plate
- power\_drill
- sugar\_box
- tomato\_soup\_can

`ros_img_segmentation.py` outputs the individual segmented images via their respective topics.

