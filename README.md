# Auto Assess Building Damage Based on Siamese Neural Network

This is a project for ECEN649 Pattern Recognition

## Docker Environment:

We use Docker to manage our training environment. To start, you need to install the docker at first. Then you can use the following command to download the docker image we uploaded to the Docker Registry:

`docker pull cloudtom/ecen649-xview2:v7-plus`

Then use:

`docker run -it cloudtom/ecen649-xview2:v7-plus`

to start the environment. You may need to add  `-v /path/to/the/code/on/your/machine:/path/in/docker/container` to mount the code repo in the Docker container

Example:
`docker run -it -v /path/to/the/code/on/your/machine:/path/in/docker/container cloudtom/ecen649-xview2:v7-plus`

## Training:

You need to visit the xView2 challenge official website https://www.xview2.org to download the dataset. And unzip the dataset into the same folder with the code.

Run `create_masks.py` at first, then run `python train_154loc.py` for training SENet154 or `python train_50loc.py` for training ResNet50

You may need to create a `wandb.ai` account to track the training process.

## Predict:

To obtain prediction image on test set, run `python pred154_loc.py` for prediction with SENet154, run `python pred50_loc.py` for prediction with ResNet50


## Compute F1 score of your result:

Please run `F1_score.ipynb`, you may need to change the image path. it will output the F1 score compared with the ground truth.


### References:

This code is inspired by gihub website: https://github.com/DIUx-xView/xView2_first_place
