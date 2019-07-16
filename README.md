# DeepLearning Malicious URLs

Detecting and Classifying Malicious URLs using Deep Learning Techniques

## Dataset

-   downloaded from: https://www.unb.ca/cic/datasets/url-2016.html
-   run FastAI-Experiments.ipynb jupyter notebook to download dataset

## Data Cleanup

-   dropped samples with Infinity and NaN values

## Datasets Summary

### All.csv

-   labeled 5 URL types with total 36697 samples
    -   build model to classify malicious URLs

| URL Type   | Total |
| ---------- | ----: |
| benign     |  7781 |
| Defacement |  7930 |
| malware    |  6712 |
| phishing   |  7586 |
| spam       |  6698 |

# Deep Learning Frameworks

-   perfomance results using various deep learning frameworks are compared

## Fastai-Pytorch

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
| Fastai-Pytorch   |        97.08 |
| Keras-Tensorflow |        91.77 |
| Keras-Theano     |           \* |

### Binary-class classification (All.csv)

-   labelled all malicious types as 1 and benign as 0

| Framework        | Accuracy (%) |
| ---------------- | -----------: |
| Fastai-Pytorch   |        98.83 |
| Keras-Tensorflow |        97.61 |
| Keras-Theano     |           \* |

# References

-   Mohammad Saiful Islam Mamun, Mohammad Ahmad Rathore, Arash Habibi Lashkari, Natalia Stakhanova and Ali A. Ghorbani, "Detecting Malicious URLs Using Lexical Analysis", Network and System Security, Springer International Publishing, P467-482, 2016.
