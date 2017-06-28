---
title: "What is a hyperparameter?"
layout: post
date: 2017-06-28 20:26
tag: [machine learning, data science]
headerImage: false
projects: false
hidden: false # don't count this post in blog pagination
description: "Intuitive explanation of what a hyperparameter is"
category: blog
author: pasankarunaratne
externalLink: false
---

A hyperparameter is a knob.

![knob]({{ site.url }}/assets/images/hyperparameter-post/knob.jpg)

It’s a knob that you tweak in your model to control its learning process.

*Hyper*parameters are a bit different from what we normally call a parameter. 

Parameters serve as a representation of your data. A *parameteric* type of model represents your data as a set of parameters.

For example, the data given below can be represented with a linear model with the parameters (m = 3, c = 7)

![linear-model-parameters]({{ site.url }}/assets/images/hyperparameter-post/linear-model.png)

In contrast to model parameters, hyperparameters do not represent data. Hyperparameters are not part of the model that describes the data. Hyperparameters are *generally* not learned and not tuned during the learning process.

Hyperparameters are the control knobs to the learning process. Some examples of hyperparameters are the learning rate (in gradient descent) or the number of leaves (in a decision tree).

---

*Fine print*

A more rigorous explanation would be that a hyperparameter encodes prior belief about how your parameters are distributed.

You pick a distribution that you think will describe your data. This distribution would have parameters (for example, the normal distribution has the parameters mean and standard deviation). If you pick a distribution that describes those parameters, the parameters of this ‘higher-level’ distribution would be the hyperparameters.

In short, hyperparameters are the parameters of a distribution that is put on the model parameters.

---
