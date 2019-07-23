# DeepLearning Malicious URLs

Detecting and Classifying Malicious URLs using Deep Learning Techniques

## Dataset

-   downloaded from: https://www.unb.ca/cic/datasets/url-2016.html
-   run FastAI-Experiments.ipynb jupyter notebook to download dataset

## Data Cleanup

-   The data for TensorFlow needed to be cleaned in way that would be easier for the ai to learn. This can be done by simply dropping samples with Infinity and NaN values, then converting the data into tensors. This is done by re-arranging the data into large arrays of 1s and 0s that the ai can understand.

- The data for Fast.AI must also be cleaned of NaN and Infinity values. Fortunately, however, after this is completed the AI should be able to read in the remainder of the data.

## Datasets Summary

### All.csv

-   labeled 5 URL types with total 36697 samples
    -   build model to classify malicious URLs

| URL Type   | Total |
| ---------- | ----: |
| benign     |  7781 |
| defacement |  7930 |
| malware    |  6712 |
| phishing   |  7586 |
| spam       |  6698 |

# Deep Learning Frameworks

-   perfomance results using various deep learning frameworks are compared

## Fast.AI

-   https://www.fast.ai/
-   uses PyTorch (https://pytorch.org/) as the backend

## Keras

-   https://keras.io/
-   using Tensorflow and Theano as backend
-   https://www.tensorflow.org/
-   https://github.com/Theano/Theano

# Results

### Multi-class classification (All.csv)

-   classification of URL types

| Framework        | Accuracy (%) |
| ---------------- | -----------: |
| Fast.AI   |        97.08 |
| Keras-TensorFlow |        96.37 |
| Keras-Theano     |           \* |

### Binary-class classification (All.csv)

-   labeled all malicious types as 1 and benign as 0

| Framework        | Accuracy (%) |
| ---------------- | -----------: |
| fast.ai   |        98.83 |
| Keras-TensorFlow |        98.62 |
| Keras-Theano     |           \* |

# References

1.   Mohammad Saiful Islam Mamun, Mohammad Ahmad Rathore, Arash Habibi Lashkari, Natalia Stakhanova and Ali A. Ghorbani, "Detecting Malicious URLs Using Lexical Analysis", Network and System Security, Springer International Publishing, P467-482, 2016.
