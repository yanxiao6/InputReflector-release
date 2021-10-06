# InputReflector

Code release of the paper "Generalizing Neural Networks by Reflecting Deviating Data in Production".

## Introduction

In this paper we describe a runtime approach that mitigates
DNN mis-predictions caused by the unexpected runtime inputs to
the DNN.

### Repo structure
- `resnet.py`: code for Resnet-20 to train the subject models
- `train_model.py`: code for ConvNet and VGG-16 to train the subject models
- `special_transformation.py`: code for transformations
- `seek_degree.py`: find the cornel degrees for each transformation
- `train.py`: train inputreflector
- `triplet_loss`: loss functions
- `eval.py`: obtain distances between given instances and training data
- `collect_auroc_sia.py`: generate AUROC from the distance
- `search_threshold_quad.py`: search for the best threshold of detecting deviated data on the validation dataset and calculate the model accuracy after calling InputReflector

### Dependencies
pip install -r requirements.txt

### How to run

- To train the subject models and InputReflector: bash log.sh
- To evaluate the performance of InputReflector: bash log_eval.sh