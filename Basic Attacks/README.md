# Basic MIA Attacks
This section of the repository contains the code for basic MIA attacks which involve using the model output, its confidence score and entropy (both normal and mixed entropy) to train a neural network in a supervised fashion to identify membership.
This repository consists of three main files,
1. basic_attacks_pretrain_priv.ipynb
2. basic_attacks_pretrain_pub.ipynb
3. basic_attacks_train.ipynb

The first two files are used to obtain the required tensors from the output target model provided, on the original images, and their horizontal and vertically flipped versions. This is then saved in a separate file (due to memory issues). Thereafter, the third file is used to train a shallow neural network with embeddings to obtain the confidence scores for each data point and make a submission on the leaderboard.

The concept behind these attacks was obtained from the previous methods section of the paper [Mitigating Membership Inference Attacks by Self-Distillation
Through a Novel Ensemble Architecture](https://www.usenix.org/system/files/sec22fall_tang.pdf) by Tang et al. (2022).
# Prerequisites
The prerequisite Python libraries for this code to run are:
1. PyTorch, TorchVision
2. Numpy, Pandas
Further, you need to make sure the private and public datasets are provided alongside the creation of the requisite directories.