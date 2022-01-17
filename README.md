# MNIST wavelet compression

Project for the Signal Analysis subject of the Master in Data Science. The main objective of the project is to explore how much the wavelet transformation and comprenssion affect to image recognition.

# Data

For this project the MNIST dataset have been used. It is composed by 70000 grayscale images of handwritten digits between 0 and 9. Images are 28 x 28 pixels and the dataset is divided into train (60000 images) and test (10000 images). More information about it can be find [here](https://www.tensorflow.org/datasets/catalog/mnist).

# Procedure

First, a convolutional model have been aplied to the original images to get a baseline. 

Then, the first wavelet level is obtained using the Haar wavelet to perform the wavelet transformation. At this point, the images have a shape of 14 x 14 pixels. The next image shows one original image and its first wavelet transformation.

![First](/Haar_wavelet_transform.png)

After the wavelet transformation a convolutional model is applied to the approximation images. Finally, the process is repeated with the second wavelet level where the images have a shape of 7 x 7. The next image shows the second wavelet transformation applied.

![Second](/Haar_2_wavelet_transform.png)

For each model the confusion matrix and some the errors the model made are plot. All the work can be find in **MNIST_Wavelet.ipynb**.

# Results


|  Image  |       Image shape      |  Image compression |  Accuracy |  Accuracy reduction |
|:--------:|:--------------:|:-----:|:---:|:---:|
| Original | 28 x 28 (784 pixels) | - | 99.03% | - |
| 1 wavelet level | 14 x 14 (196 pixels) | 75.00% | 99.02% | 0.01% |
| 2 wavelet level | 7 x 7 (49 pixels) | 93.75% | 97.09% | 1.95% |

With the original images of 28 x 28 (784 pixels) the accuracy is 99.03%. With a compression to 14 x 14  images (196 pixels, 75% of reduction) the accuracy only goes down to a 99.02% (only a 0.01% of reduction). Finally, with a compression to 7 x 7 images (49 pixels, 93.75% of reduction) the accuracy goes down to 97.09% (reduction of 1.95%).

