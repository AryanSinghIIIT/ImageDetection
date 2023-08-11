
A generic image detection program that uses Google's Machine Learning library, [Tensorflow](https://www.tensorflow.org/) and a pre-trained Deep Learning Convolutional Neural Network model called [Inception](https://research.googleblog.com/2016/03/train-your-own-image-classifier-with.html).

This model has been pre-trained for the [ImageNet](http://image-net.org/) Large Visual Recognition Challenge using the data from 2012, and it can differentiate between 1,000 different classes, like Dalmatian, dishwasher etc.
The program applies Transfer Learning to this existing model and re-trains it to classify a new set of images.

This is a generic setup and can be used to classify almost any kind of image. I created a small demo that classifies two image data sets - cat and dog images, and returns a prediction score denoting the possibility of it being an image of a cat or a dog.

<br/>

## Installation
Make sure you have [Python 3](https://www.python.org/downloads/) installed, then install [Tensorflow](https://www.tensorflow.org/install/) on your system, and clone this repo.

<br/>

## Usage

### Prepare the image data sets
In order to start the transfer learning process, a folder named ``training_dataset`` needs to be created in the root of the project folder. This folder will contain the image data sets for all the subjects, for whom the classification is to be performed.

Create the ``training_dataset`` folder and add the images for all the data sets in the following manner -

```javascript
/
|
|ar
---- /training_dataset
|    |
|    |
|    ---- /cat
|    |    cat1.jpg
|    |    cat2.jpg
|    |    ...
|    |
|    |
|    ---- /dog
|         dog1.jpg
|         dog2.jpg
|         ...
|
|     
```
This enables classification of images between the ``cat`` and ``dog`` data sets.

> Make sure to include multiple variants of the subject (side profiles, zoomed in images etc.), the more the images, the better is the result.

### Initiate transfer learning
Go to the project directory and run -

```javascript
$ bash train.sh
```
This script installs the ``Inception`` model and initiates the re-training process for the specified image data sets.

Once the process is complete, it will return a training accuracy somewhere between ``85% - 100%``.

The ``training summaries``, ``retrained graphs`` and ``retrained labels`` will be saved in a folder named ``tf_files``.

### Classify objects
![file-dialog1](https://github.com/AryanSinghIIIT/ImageDetection/assets/96579866/d3c30694-5f9d-41a9-b938-b14917206934)

```javascript
python3 classify.py
```

This opens up the file dialog using which you can select your input file.


Once the input file is selected, the classifier will output the predictions for each data set. A prediction score between ``0.8`` to ``1`` is considered to be optimal.
![cli-output1](https://github.com/AryanSinghIIIT/ImageDetection/assets/96579866/3169ceb3-0639-4d9c-b00c-1e7224ebe7e6)


<br/>

## Results
![result](https://github.com/AryanSinghIIIT/ImageDetection/assets/96579866/6f6fcd40-8038-4070-a4e2-2bdda92e8069)

<br/>



<br/>



