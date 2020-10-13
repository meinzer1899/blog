---
toc: true
layout: post
description: Lesson1 of fast.ai's 2020 course covers topics like limitations and
things where machine learning models are good at, pretrained models, image
classification and also gives hints on datasets. Here is my summary.
categories: [fast.ai, 2020, summary, lesson 1]
comments: true
image: images/2020-10-12/teddy-post.jpeg
title: Lesson 1 summary
---

# Limitations Inherited to ML

A model cannot be created without data. Models outputs are *predictions*, not
*actions*. The data can be divided into

1. a training set,
2. a validation set, and
3. (optionally) a test set.

@startuml
Bob -> Alice
@enduml

A training set roughly consists of 70&nbsp;% of the data and is used to train the
model. A validation set&mdash;used to validate the models performance&mdash;of
20&nbsp;% is accomplished by a test set of 10&nbsp;%.

{% include info.html text="Model goals" %}
We want a model to predict previously unseen data by finding general
*patterns* in the data it is trained with, called **generalization**. The thing 
do is called **memorization**&mdash;memorize all data it was shown and so fail
at previously unseen data. One sign our model tries to memorize instead of
finding general patterns in our data is by *overfitting*.

## Pretrained Model
A pretrained model is a model which weights already have been trained by
experts for a specific task, e.g. image recognition with *ImageNet* dataset.

With *transfer learning*, a pretrained model is used to accomplish a different
task. TODO: give example
With a pretrained model, the learning process requires much less performance and
time, because weights only have to be adjusted, not learned by the model from
scratch.

{% include warning.html text="The importance of pretrained models arent covered
good enough in books and courses" %}

## Image classification
**Imag**in**e** what you can turn into images: audio signals, movements, or time
series. This can be used to let models for image classification for different
tasks. For example, a model trained for mouse movement images can be used for
malware detection.

Model accuracy can be increased by *segmentation*&mdash;recognize every pixel of
an image

## Dataset tipps
Without good data, a model cannot achieve good results (garbage in, garbage out
principle). Use cut-down versions of datasets&mdash;subsets of the
dataset&mdash;for prototyping and experimenting.

*Hyperparameters* are parameters about parameters.

Training set trains the model. The model *sees* this data.
Validation set validates performance (improves) the model. We see the data.
Test set evaluates the model at the very end of our efforts. Neither the model
nor we see this data until the very end.
