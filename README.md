# Object-Recognition-using-ResNet50
# README

This repository contains code for working with the CIFAR-10 dataset using two different approaches: a simple Neural Network and a more complex ResNet50 model. The CIFAR-10 dataset is a widely used dataset for image classification tasks. It consists of 60,000 32x32 color images in 10 classes, with 6,000 images per class. Below are the steps to set up the environment and run the code.

## CIFAR-10 Dataset Description

The CIFAR-10 dataset consists of the following classes:

1. Airplane
2. Automobile
3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse
9. Ship
10. Truck

Each class contains 6,000 images, making a total of 60,000 images in the dataset. The images are of size 32x32 pixels and are in RGB color format. This dataset is commonly used for training machine learning models in the field of computer vision.

## Prerequisites

Make sure you have the following installed in your Python environment:

- [Kaggle API](https://github.com/Kaggle/kaggle-api)
- [Py7zr](https://pypi.org/project/py7zr/)
- [TensorFlow](https://www.tensorflow.org/install)

## Getting Started

1. Install the required packages:

   ```bash
   !pip install kaggle py7zr tensorflow
   ```

2. Configure the Kaggle API and download the CIFAR-10 dataset:

   ```bash
   !mkdir -p ~/.kaggle
   !cp kaggle.json ~/.kaggle/
   !chmod 600 ~/.kaggle/kaggle.json
   !kaggle competitions download -c cifar-10
   ```

3. Extract the downloaded dataset:

   ```python
   from zipfile import ZipFile
   
   dataset = '/content/cifar-10.zip'
   
   with ZipFile(dataset, 'r') as zip:
       zip.extractall()
       print('The dataset is extracted')
   ```

4. Extract the images using Py7zr:

   ```python
   import py7zr
   
   archive = py7zr.SevenZipFile('/content/train.7z', mode='r')
   archive.extractall()
   archive.close()
   ```

5. Run the provided Python code to process the images and train the models. The code includes steps for loading, processing, and splitting the data, building and training the Neural Network and ResNet50 model, and evaluating the models' performance.

