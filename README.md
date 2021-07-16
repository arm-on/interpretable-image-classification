Interpretability methods applied on image classifiers trained on MNIST and CIFAR10
---
This repo includes the files (jupyter notebooks) for the interpretation of two deep neural networks capable of classifying 0-9 digits based on the images belonging to the MNIST dataset, and ten categories (including "airplane", "automobile", "bird", "cat", "deer", "dog", "frog", "horse", "ship", and "truck") of the CIFAR10 dataset. 

The project includes some phases:
- Training neural networks on the datasets
  
  In this phase, we trained two deep neural networks. One of them was trained on the MNIST dataset of images, and the other one on CIFAR10. Both of the neural networks achieve accuracy greater than 93% both on the training and testing datasets. We were curious to see if the networks had really learned to extract a good set of features, and operated based on them.
- Implementing interpretability methods
  
  To answer the question of the previous phase, we implemented three interpretability methods including LIME, Kernel SHAP (KSHAP), and Layer-wise Relevance Propagation (LRP)
- Comparing methods based on visualization

  Note that each of the two datasets include 10 categories of images. For each dataset, 3 pictures were chosen from each category, randomly. Then, the 30 resulting images were passed to the neural nets, and their interpretability results were generated by the three methods (LIME, KSHAP, and LRP). The results suggest that the LRP method performs far better than the other two methods. This might be related to the fact that this method is specialized for the deep neural networks.
  
  
- Comparing methods based on the models

  In this phase, we tried to compare the methods based on the degradation of accuracy the cause for the models. More specifically, we first generated an unreal testing set based on the real one. This was done by taking the top 20% of the most important pixels of each image, and replacing it by 0 or 255 (a kind of salt and pepper noise was added to the testing dataset while keeping only a small percentage of the most important pixels unchanged). After feeding each network with only 20% of the useful information, its accuracy on the new testing set was calculated. Note that "the most important pixels" were determined by the three previously mentioned interpretability methods (they are not necessarily correct though! right?). 
  
- Interpretability in Bayesian Neural Networks

  The last step includes training a bayesian neural net. This network's architecture is much simpler than the previous ones (only includes some linear layers nonlinearized by "ReLU" activations). However, the weights and biases in this network are assumed to be random variables each coming from the Normal distribution. The mean and variance of these distributions were tuned during the training.
  
Acknowledgements
---
This project was done as a course project for the <a href="http://ce.sharif.edu/courses/99-00/2/ce729-1/">Statistical Machine Learning (SML) course offered by Sharif University of Technology on Spring 2021</a>.
