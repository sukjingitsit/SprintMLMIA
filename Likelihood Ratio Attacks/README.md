# Likelihood Ratio Attack
In this folder, the code for implementing the likelihood Ratio Attack (LiRA) as mentioned in [Membership Inference Attacks From First Principles](https://arxiv.org/pdf/2112.03570)

## Description

The code for this has been implemented using the offline attack algorithm, where shadow models are trained on subsets of the population (which may or may not necessarily intersect with the training code). Each file, and its corresponding contribution to the attack is explained herewith:
1. division_code.ipynb

    This code is used to divide the given dataset, where both private and public contain 20,000 points each into 32 (N) separate partitions which are class balanced and contain 20,000 points. This serves to provide 2N models where for each points there are N IN and N OUT models.

2. shadow_model_training.ipynb

    This code was run on Kaggle to speed up training on the shadow models using the output files of the previous notebook. The training uses random horizontal and vertical flips as mentioned in the document.

3. LiRA_inference.ipynb

    This code evaluates the 2N models and saves the confidence scores obtained on the four flips of the image into a tensor before statistically calculating the likelihood ratio. This is because inference for all the models and points takes quite a substantial amount of time to run

4. LiRA_submission.ipynb
    
    Here, the mean and variance of the confidence for the IN and OUT scores is calculated for each point, and using the likelihood ratio on the four possible orientations of the image, a final likelihood value is computed as their geometric mean. This differs from the paper which suggests using a multivariate normal distribution for augmentations instead.

## Prerequisites
The prerequisite Python libraries for this code to run are:
1. PyTorch, TorchVision
2. Numpy, Pandas, Scipy
Further, you need to make sure the private and public datasets are provided alongside the creation of the requisite directories.