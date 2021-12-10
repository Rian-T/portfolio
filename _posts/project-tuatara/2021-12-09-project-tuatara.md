---
layout: post
title: Project Tuatara - Autonomous car competition
date: 2021-11-29 01:00 +0700
description: We are participating with a friend in an autonomous car competition. We are trying to make our car race as fast as possible using deep learning.
tag:
  - deep learning
  - reinforcement learning
image: /assets/project-tuatara/roadregression.gif
---

With a friend of mine, [Armand du Parc Locmaria](https://twitter.com/armand_dpl), we are participating in an autonomous car competition. We are trying to make our car go as fast as possible using deep learning.

Armand built the car and has done everything related to the hardware. I was more focused on model training and the simulation environement.

### Regression of the center of the road

Our first approach was to use a neural network to predict the center of the road. We trained a CNN on images of the road we gathered from the car and we labeled the center.

![Road Regression](/assets/project-tuatara/roadregression.gif)

We used [ResNet34](https://arxiv.org/abs/1512.03385) as our CNN. It was pre-trained on the [ImageNet](https://www.image-net.org/) dataset.

### sim2real

Our second approach was to train the car in the donkey gym environnement.

![Road Regression](/assets/project-tuatara/donkey-gym.gif)

We used SAC and PPO as our algorithms using stable-baselines3. We also used [wandb](https://docs.wandb.com/) to log experiments.

We also tried our first model in the simulation which, to our surprise, worked pretty well.

You can find the code [on github here](https://github.com/Armandpl/tuatara).

## Challenges

One of the biggest challenge is that our model needs to be able to adapt to any road. The competition is not always in the same place and it's obviously different from where we train.

To overcome that, we tried data augmentation.

![Data augmentation](/assets/project-tuatara/data_augmentation.png)
*Example of data augmentation on a batch*

We tried channel inversion, random grayscale, random motion blur and random erasing.

Thanks to this, the mean episode duration has a little bit increased, which means less crashes but it is still not satisfying.

## Technologies used

- [PyTorch](https://pytorch.org/)
- [PyTorch Lightning](https://pytorch-lightning.readthedocs.io/)
- [OpenAI Gym](https://openai.com/blog/introduction-to-openai-gym/)
