# Interpretable Image Classification (IIC)

Interpretability methods applied on image classifiers trained on MNIST and CIFAR10
---
This repo includes the files (jupyter notebooks) for the interpretation of two deep neural networks capable of classifying 0-9 digits based on the images belonging to the <a href="http://yann.lecun.com/exdb/mnist/">MNIST</a> dataset, and ten categories (including "airplane", "automobile", "bird", "cat", "deer", "dog", "frog", "horse", "ship", and "truck") of the <a href="https://www.cs.toronto.edu/~kriz/cifar.html">CIFAR10</a> dataset. 

Project Phases
---
The project includes some phases:
- Training neural networks on the datasets [<a href="https://github.com/arm-on/interpretable-image-classification/tree/main/training">Code</a>]
  
  In this phase, I trained two deep neural networks. One of them was trained on the MNIST dataset of images, and the other one on CIFAR10. Both of the neural networks achieve accuracy greater than 93% both on the training and testing datasets. I was curious to see if the networks had really learned to extract a good set of features, and operated based on them.
- Implementing interpretability methods [<a href="https://github.com/arm-on/interpretable-image-classification/tree/main/interpretability-methods">Code</a>]
  
  To answer the question of the previous phase, I implemented three interpretability methods including LIME, Kernel SHAP (KSHAP), and Layer-wise Relevance Propagation (LRP)
- Comparing methods based on visualization [<a href="https://github.com/arm-on/interpretable-image-classification/tree/main/visualization-comparison">Code</a>]

  Note that each of the two datasets include 10 categories of images. For each dataset, 3 pictures were chosen from each category, randomly. Then, the 30 resulting images were passed to the neural nets, and their interpretability results were generated by the three methods (LIME, KSHAP, and LRP). The results suggest that the LRP method performs far better than the other two methods. This might be related to the fact that this method is specialized for the deep neural networks.
  
  
- Comparing methods based on the models [<a href="https://github.com/arm-on/interpretable-image-classification/tree/main/degradation-comparison">Code</a>]

  In this phase, I tried to compare the methods based on the degradation of accuracy the cause for the models. More specifically, I first generated an unreal testing set based on the real one. This was done by taking the top 20% of the most important pixels of each image, and replacing it by 0 or 255 (a kind of salt and pepper noise was added to the testing dataset while keeping only a small percentage of the most important pixels unchanged). After feeding each network with only 20% of the useful information, its accuracy on the new testing set was calculated. Note that "the most important pixels" were determined by the three previously mentioned interpretability methods (they are not necessarily correct though! right?). 
  
- Interpretability in Bayesian Neural Networks [<a href="https://github.com/arm-on/interpretable-image-classification/tree/main/bayesian-nn">Code</a>]

  The last step includes training a bayesian neural net. This network's architecture is much simpler than the previous ones (only includes some linear layers nonlinearized by "ReLU" activations). However, the weights and biases in this network are assumed to be random variables each coming from the Normal distribution. The mean and variance of these distributions were tuned during the training.
  
Cite
---
Please cite this github repo in your publication if you are using "Interpretable Image Classifiers" (IIC) in your research:
```
@misc{iic2021,
  author={Malekzadeh, Arman},
  title = {Interpretable Image Classifiers},
  year = {2021},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/arm-on/interpretable-image-classification/}},
}
```

Report
---
For now, a complete report is available for the project in Persian (check the <a href="https://github.com/arm-on/interpretable-image-classification/tree/main/report">"report" folder</a>). An English version of the report might be added later.

<!--Contact
---
Please do not hesitate to ask your questions from us. For any details or discussions about the repo, you can open an issue, or send an email to <a href="mailto:malekzadeh@ieee.org">malekzadeh@ieee.org</a>. -->

Acknowledgements
---
This project was done as a course project for the <a href="http://ce.sharif.edu/courses/99-00/2/ce729-1/">Statistical Machine Learning (SML) course offered by Sharif University of Technology on Spring 2021</a> instructed by <a href="http://sharif.edu/~rabiee/">Prof. Rabiee</a>.
