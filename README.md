This project aims to explore the data in search of hidden patterns using **non deep learning** classification tools. The findings will be analyzed in context of **clinical aspects** using interactive data visualizations. This way I hope to establish a robust understanding of machine learning in context of healthcare. 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://drive.google.com/file/d/1npMIKc5VYEOwgVK2079-wju3kuxSeDBT/view?usp=sharing)

[<img src='https://github.com/Daniboy370/Uploads/blob/master/logo-Medium.png?raw=true' width=110 />](https://medium.com/@danielengelsman/say-hello-to-doctor-ai-b32448ed5d52)

[<img src='https://upload.wikimedia.org/wikipedia/commons/7/7c/Kaggle_logo.png' width=65 />](https://www.kaggle.com/daniboy370/can-ai-outperform-radiologists)



Contents
--------
<!--ts-->
+ [Abstract](#Abstract)
+ [Method](#Method)
+ [Results](#Results)
+ [Requirements](#Requirements)
<!--te-->

Abstract
------------
The project is based on the Wisconsin Breast Cancer Dataset ([WBCD](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic))) and aims
to implemenet ML algorithms for an accurate diagnosis of cancerous cells :

&nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  <img src='https://github.com/Daniboy370/Machine-Learning/blob/master/Misc/Latex/Images/Intro_1.png?raw=true' width=550 />

Discrimination between malignant and benign cells, can be obtained by digesting and extracting meaningful faetures, 
**before** delivered to the classifier. The raw dataset (including indices and id) after applying random shuffling:

&nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; <img src='https://github.com/Daniboy370/Machine-Learning/blob/master/Misc/Latex/Images/data_table.png' width=850 />

Method
-------
After thorough inspection and investigation of the data, the samples undergo PCA, where each variable (feature) has an associated 
red arrow (after scaling factor), in the directions that maximize each of the PC’s variance. Consider the following 3D demonstration :

&nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; <img src='https://github.com/Daniboy370/Machine-Learning/blob/master/Misc/Animation/PCA_vid.gif' width=700 />

The blue points are benign instances after compression (PCA) to the 3D space. The orange denote malignant instances. Note how the 
Concave points feature maximizes the 1st PC's variance. Contrarily, Fractal dimension and Symmetry, contribute poorly to the 3rd PC. 

The **ROC** reflects a binary classifier ability to discriminate classes, using a probabilistic analysis.
Each threshold is a point on the ROC graph, denoting the **TPR/FPR** tradeoff :

&nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; <img src='https://github.com/Daniboy370/Machine-Learning/blob/master/Misc/Latex/Images/Results_1.png' width=600 />

Results
-------
By performing the following pipeline, the performance can be concentrated :

&nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; ![alt text](https://github.com/Daniboy370/Machine-Learning/blob/master/Misc/Latex/Images/Table.png?raw=true)

All classifiers exhibit satsfactory results, but the SVM outperformed all. Being honest, the relatively modest amount of samples in 
the dataset, that may cause overfitting. Therefore, the classifiers results showed slight sensitivity each the random initialization.

The following figure presents data projection into 2D coordinate system, and applying different classification tools :

&nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; <img src='https://github.com/Daniboy370/Machine-Learning/blob/master/Misc/Latex/Images/Decision.png?raw=true' width=700 />

It is interesting to see how decision boundaries are largely influenced by differenet classification methods 🧐.

## Citation
* Wisconsin Breast Cancer Dataset ([WBCD](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic))) :
```
@misc{Dua:2019 ,
author = "Dua, Dheeru and Graff, Casey",
year = "2017",
title = "{UCI} Machine Learning Repository",
url = "http://archive.ics.uci.edu/ml",
institution = "University of California, Irvine, School of Information and Computer Sciences" }
```

##  Requirements
* Google [[Colab](https://colab.research.google.com/notebooks/intro.ipynb)] or at least Python 3.4.

* List of imported packages can be found in the first block of ***ML_Proj.ipynb***.
