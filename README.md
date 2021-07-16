Interpretability methods applied on image classifiers trained on MNIST and CIFAR10
---
This repo includes the files (jupyter notebooks) for the interpretation of two deep neural networks capable of classifying 0-9 digits based on the images belonging to the MNIST dataset, and ten categories (including "airplane", "automobile", "bird", "cat", "deer", "dog", "frog", "horse", "ship", and "truck") of the CIFAR10 dataset. 

The project includes some phases:
- Training neural networks on the datasets
  In this phase, we trained two deep neural networks. One of them was trained on the MNIST dataset of images, and the other one on CIFAR10. Both of the neural networks achieve accuracy greater than 93% both on the training and testing datasets. We were curious to see if the networks had really learned to extract a good set of features, and operated based on them.
- Implementing interpretability methods
  To answer the question of the previous phase, we implemented three interpretability methods including LIME, Kernel SHAP (KSHAP), and Layer-wise Relevance Propagation (LRP)
- Comparing methods based on visualization
- Comparing methods based on the models
- Interpretability in Bayesian Neural Networks
