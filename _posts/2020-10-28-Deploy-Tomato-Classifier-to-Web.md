---
toc: true
layout: post
description: In Lesson 2 of fast.ai 2020 course, Jeremy and co deploy a Bear classifier to the Web. In this post, I describe how I used the course material to train and deploy a model that can classify tomatoes to the web.
categories: [fast.ai 2020]
comments: true
image: images/icons/tomato.jpeg
title: Deploy Tomato Classifier to Web
---

## Introduction

In lesson 2 of fast.ai course 2020, we are going straight into production.
Jeremy makes good on his promise of a _top down_ approach: Get your hands dirty
and bring models to production and find out the details afterwards.

## Train the Model

To train the model to classify tomatoes, we use _Bing Search_ to download 150
images each for three tomato sorts we want to classify (_Ochsenherz_, _Latah_
and _Paulinchen_). After the training is done, we validate the model. Following
the tipp from the course, we observe the training data with the GUI provided by
the fast.ai API. With the API, we can assign the appropiate labels to the images
or delete images which may not contain a tomato at all. While observing the
images, I found a lot of images which I have to delete or modify.

## Deploy to the Web

The goal is to make the model usable to everyone by deploying it to the web.
There were two possibilities:

- using [binder](https://www.mybinder.org) or
- the cloud application plattform [Heroku](www.heroku.com).

You have to make sure that _Voilà_ is used. You specify the additional packages
you need in `requirements.txt`. The `Procfile` tells _Heroku_ which parameters
to use when deplying to the web. The [course
homepage](https://course.fast.ai/deployment_heroku#requirementstxt) describes
best how to deploy with _Heroku_.

You want to try out the results? I'm happy you ask. Check our the [tomato
classifier repository](https://github.com/meinzer1899/tomatoClassifier) and use
the app by clicking on either the binder badge or the environments link on the
right hand side.
