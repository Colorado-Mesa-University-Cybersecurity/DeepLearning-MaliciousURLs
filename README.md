# Deep Learning Malicious URLs

Detecting and Classifying Malicious URLs using Deep Learning Techniques

## Dataset

-   downloaded from: https://www.unb.ca/cic/datasets/url-2016.html
-   run FastAI-Experiments.ipynb jupyter notebook to download dataset

## Data Cleanup

-   dropped samples with NaN and Infifinity and mising values

## Datasets Summary

### All.csv

-   labeled 5 URL types with total 36697 samples
    -   goal is to build model that dectets and classifies malicious URLs

| URL Type   | Total |
| ---------- | ----: |
| benign     | 7,781 |
| defacement | 7.930 |
| malware    | 6,712 |
| phishing   | 7,586 |
| spam       | 6,698 |

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
| Fast.AI          |        97.08 |
| Keras-TensorFlow |        96.37 |
| Keras-Theano     |           \* |

### Binary-class classification (All.csv)

-   labeled all malicious types as 1 and benign as 0

| Framework        | Accuracy (%) |
| ---------------- | -----------: |
| fast.ai          |        98.83 |
| Keras-TensorFlow |        98.62 |
| Keras-Theano     |           \* |

# References

1.  Mohammad Saiful Islam Mamun, Mohammad Ahmad Rathore, Arash Habibi Lashkari, Natalia Stakhanova and Ali A. Ghorbani, "Detecting Malicious URLs Using Lexical Analysis", Network and System Security, Springer International Publishing, P467-482, 2016.
