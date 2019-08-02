# Deep Learning Models to Detect and Classify Malicious URLs

This research project compares the accuracies of varioius machine and deep learning frameworks in detecting
and classifying malicious URLs using lexcial features.

## Dataset

-   downloaded from: https://www.unb.ca/cic/datasets/url-2016.html
-   run Baseline-Experiments.ipynb jupyter notebook to download dataset using provided Bash script

## Data Cleanup

-   dropped samples and attributes with NaN, Infifinity and mising values
-   removed whitespaces from column/attribute names

## Datasets Summary

-   labeled 5 URL types with total 36,707 samples (before cleanup)
-   consists of 79 lexical features extracted from URLs
-   table below shows original sample counts (Total) and New Totals (after data cleanup)
-   Total (Dropping NaN Rows) - remaining total samples after dropping samples with NaN values
    -   ~17K rows were dropped
-   Total (Dropping NaN Cols) - remaining total samples after dropping columns/attributes with NaN values
    -   7 attributes are dropped as a result with total 72 attributes remaining

| Dataset | URL Type   |  Total | Total (Dropping NaN Rows) | Total (Dropping NaN Cols) |
| ------- | ---------- | -----: | ------------------------: | ------------------------: |
| All.csv | benign     |  7,781 |                     2,709 |                     7,781 |
|         | defacement |  7.930 |                     2,477 |                     7,930 |
|         | malware    |  6,712 |                     4,440 |                     6,711 |
|         | phishing   |  7,586 |                     4,014 |                     7,577 |
|         | spam       |  6,698 |                     5,342 |                     6,698 |
|         | malicious  | 28,926 |                    16,273 |                    28,916 |

## Machine Learning Algorithms

-   perfomance results using various machine learning algorithms and deep learning frameworks are compared
-   authors of the dataset[1] have used 3 classifiers
    -   C4.5 (Decision Tree)
    -   KNN (K-Nearest Neighbors)
    -   RF (Random Forest)
    -   RF achieved the best results
        -   0.97 Precision and 0.97 Recall on Multi-class
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

### fast.ai

-   https://www.fast.ai/
-   uses PyTorch (https://pytorch.org/) as the backend

### Keras

-   https://keras.io/
-   using Tensorflow and Theano as backend
-   https://www.tensorflow.org/
-   https://github.com/Theano/Theano

## Model Evaluations

-   use 10-fold cross validation to estimate accuracy results
-   split dataset into 10 parts, train on 9 and test on 1 and repeat for all combination of train-test splits
-   calculate the average accuracy

## Experiments and Results

### Multi-class Classification (All.csv)

-   classification of URL types (benign, malware, spam, phishing, defacement)

### Machine Learning Algorithm Results

#### Results on Dataset after Dropping NaN Rows

-   Comparision of Algorithms using Box plot
    ![](./images/MLComparisonsDroppedRows.png)

-   Validation Results from Best Classifer (Random Forest)
-   Confusion Matrix
    ![](./images/RFConfusionDroppedRows.png)
-   Classification Report:

    |              | precision | recall | f1-score | support |
    | ------------ | --------- | -----: | -------: | ------: |
    | defacement   | 0.97      |   0.95 |     0.96 |     526 |
    | benign       | 0.95      |   0.97 |     0.96 |     546 |
    | malware      | 0.98      |   0.98 |     0.98 |     913 |
    | phishing     | 0.91      |   0.93 |     0.92 |     764 |
    | spam         | 0.99      |   0.98 |     0.98 |    1048 |
    |              |           |        |          |         |
    | accuracy     |           |        |     0.96 |    3797 |
    | macro avg    | 0.96      |   0.96 |     0.96 |    3797 |
    | weighted avg | 0.96      |   0.96 |     0.96 |    3797 |

#### Results on Dataset after Dropping NaN Columns

-   Comparision of Algorithms using Box-plot
    ![](./images/MLComparisonsDroppedCols.png)

-   Validation Results from Best Classifer (Random Forest)
-   Confusion Matrix
    ![](./images/RFConfusionDroppedCols.png)
-   Classification Report:

```
              precision    recall  f1-score   support

  Defacement       0.98      0.98      0.98      1594
      benign       0.97      0.98      0.98      1541
     malware       0.99      0.98      0.98      1367
    phishing       0.95      0.95      0.95      1523
        spam       0.99      0.97      0.98      1315

    accuracy                           0.97      7340
   macro avg       0.97      0.97      0.97      7340
weighted avg       0.97      0.97      0.97      7340
```

### Deep Learning Framework Results

| Framework        | CPU Accuracy (%) | GPU Accuracy (%) | TPU Accuracy (%) |
| ---------------- | ---------------: | ---------------: | ---------------: |
| Fast.AI          |            97.08 |            97.23 |            97.26 |
| Keras-TensorFlow |            96.37 |            95.79 |            95.60 |
| Keras-Theano     |               \* |               \* |               \* |

### Binary-class Classification (All.csv)

-   re-labeled defacement, malware, phishing, spam, defacement as malicious type (1) and benign as 0
-   detecting malicious URLs (malicious Vs benign)

### Machine Learning Algorithm Results

#### Results on Dataset after Dropping NaN Rows

-   Comparision of Algorithms using Box plot
    [](images/MLComparisonsDroppedRowsBinary.png)

-   Validation Results from Best Classifer (Random Forest)
-   Confusion Matrix
    [](images/RFConfusionDroppedRowsBinary.png)
-   Classification Report:

```
              precision    recall  f1-score   support

      benign       0.95      0.98      0.97       546
   malicious       1.00      0.99      0.99      3251

    accuracy                           0.99      3797
   macro avg       0.97      0.99      0.98      3797
weighted avg       0.99      0.99      0.99      3797
```

#### Results on Dataset after Dropping NaN Columns

-   Comparision of Algorithms using Box-plot
    [](images/MLComparisonsDroppedColsBinary.png)

-   Validation Results from Best Classifer (Random Forest)
-   Confusion Matrix
    [](images/RFConfusionDroppedColsBinary.png)
-   Classification Report:

```
              precision    recall  f1-score   support

      benign       0.97      0.98      0.98      1541
   malicious       0.99      0.99      0.99      5799

    accuracy                           0.99      7340
   macro avg       0.98      0.99      0.98      7340
weighted avg       0.99      0.99      0.99      7340
```

### Deep Learning Framework Results

| Framework        | CPU Accuracy (%) | GPU Accuracy (%) | TPU Accuracy (%) |
| ---------------- | ---------------: | ---------------: | ---------------: |
| Fast.AI          |            98.83 |            98.62 |            98.73 |
| Keras-TensorFlow |            98.62 |            98.70 |            98.79 |
| Keras-Theano     |               \* |               \* |               \* |

# References

1.  Mohammad Saiful Islam Mamun, Mohammad Ahmad Rathore, Arash Habibi Lashkari, Natalia Stakhanova and Ali A. Ghorbani, "Detecting Malicious URLs Using Lexical Analysis", Network and System Security, Springer International Publishing, P467-482, 2016.

-   Your First Machine Learning Project in Python Step-by-Step - https://machinelearningmastery.com/machine-learning-in-python-step-by-step/
