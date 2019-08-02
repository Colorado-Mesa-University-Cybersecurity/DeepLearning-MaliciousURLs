# Deep Learning Models to Detect and Classify Malicious URLs

This research project studies the efficiencies of varioius deep learning frameworks in detecting
and classifying malicious URLs using lexcial features.

## Dataset

-   downloaded from: https://www.unb.ca/cic/datasets/url-2016.html
-   run Baseline-Experiments.ipynb jupyter notebook to download dataset using provided Bash script

## Data Cleanup

-   dropped samples with NaN and Infifinity and mising values

## Datasets Summary

-   labeled 5 URL types with total 36,707 samples (before cleanup)
-   consists of 79 lexical features extracted from URLs
-   table shows original sample counts (Total) and New Totals (after data cleanup)
-

| File    | URL Type   | Total | Total (Dropped NaN Rows) | Total (Dropped NaN Cols) |
| ------- | ---------- | ----: | -----------------------: | -----------------------: |
| All.csv | benign     | 7,781 |                    2,709 |                          |
|         | defacement | 7.930 |                    2,477 |                          |
|         | malware    | 6,712 |                    4,440 |                          |
|         | phishing   | 7,586 |                    4,014 |                          |
|         | spam       | 6,698 |                    5,342 |                          |
|         | malicious  |       |                          |                    28916 |

## Machine Learning Algorithms

-   authors of the dataset[1] have used
    -   C4.5 (Decision Tree)
    -   KNN (K-Nearest Neighbors)
    -   RF (Random Forest)
    -   RF achieved the best results
        -   0.97 Precision and 0.97 Recall on multi-class
        -   0.99 Precision and 0.99 on (Single-class)
-   we evaluate 9 algorithms
    1. Logistic Regression (LR)
    -   Linear Discriminant Analysis (LDA)
    -   K-Nearest Neighbors (KNN)
    -   Classification and Regression Trees (CART)
    -   Gaussian Naive Bayes (NB)
    -   Support Vector Machines (SVM)
    -   Random Forest (RF)
    -   Decision Tree (DT)
    -   Ada Boost (AB)
-   2 simple linear classifiers (LR and LDA)
-   5 nonlinear (KNN, CART, NB, SVM, and DT)
-   2 Ensemble-based (RF, AB)

## Deep Learning Frameworks

-   perfomance results using various machine learning algorithms and deep learning frameworks are compared

## fast.ai

-   https://www.fast.ai/
-   uses PyTorch (https://pytorch.org/) as the backend

## Keras

-   https://keras.io/
-   using Tensorflow and Theano as backend
-   https://www.tensorflow.org/
-   https://github.com/Theano/Theano

## Model Evaluations

-   use 10-fold cross validation to estimate accuracy results
-   split out dataset into 10 parts, train on 9 and test on 1 and repeat for all combination of train-test splits
-   calculate the average accuracy

## Results

### Multi-class classification (All.csv)

-   classification of URL types

| Framework        | CPU Accuracy (%) | GPU Accuracy (%) | TPU Accuracy (%) |
| ---------------- | ---------------: | ---------------: | ---------------: |
| Fast.AI          |            97.08 |            97.23 |            97.26 |
| Keras-TensorFlow |            96.37 |            95.79 |            95.60 |
| Keras-Theano     |               \* |               \* |               \* |

### Binary-class classification (All.csv)

-   re-labeled defacement, malware, phishing, spam, defacement as malicious type (1) benign as 0

| Framework        | CPU Accuracy (%) | GPU Accuracy (%) | TPU Accuracy (%) |
| ---------------- | ---------------: | ---------------: | ---------------: |
| Fast.AI          |            98.83 |            98.62 |            98.73 |
| Keras-TensorFlow |            98.62 |            98.70 |            98.79 |
| Keras-Theano     |               \* |               \* |               \* |

# References

1.  Mohammad Saiful Islam Mamun, Mohammad Ahmad Rathore, Arash Habibi Lashkari, Natalia Stakhanova and Ali A. Ghorbani, "Detecting Malicious URLs Using Lexical Analysis", Network and System Security, Springer International Publishing, P467-482, 2016.

-   Your First Machine Learning Project in Python Step-by-Step - https://machinelearningmastery.com/machine-learning-in-python-step-by-step/
