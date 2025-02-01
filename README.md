# Overview of the Repository

This repository contains an implementation of two membership inference attack methods for a SprintML challenge. A detailed description of the methods and their implementation is available in the subdirectories. Of these, the LiRA attack is the most successful on both the TPR@FPR=0.05 and AUC metric commonly used to evaluate membership inference attacks. There are plans to further extend this implementation for RMIA, albeit currently that has not been done due to resource constraints.

## Prerequisites
The prerequisite Python libraries for this code to run are:
1. PyTorch, TorchVision
2. Numpy, Pandas, Scipy

Further, you need to make sure the private and public datasets are provided alongside the creation of the requisite directories.