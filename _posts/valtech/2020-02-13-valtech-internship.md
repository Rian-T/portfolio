---
layout: post
title: Image segmentation and image generation of shoes
date: 2020-02-13 01:00 +0700
description: This was my first technical internship. I had to segment the different part of the shoes and generate new shoes using GANs.
tag:
  - deep learning
  - GAN
---

I was given the opportunity to do an internship at Valtech where I worked on applications of Deep Learning in the fashion industry.

## Image segmentation

The first task I was assigned was to segment shoes from the background and then segment the different parts of the shoes.

![Image segmentation using M-RCNN](/assets/valtech/mrcnn.png)
*Image segmentation using M-RCNN*

For that I compared the performance of M-RCNN and U-Net using pixel-wise accuracy and intersection over union.

![Image segmentation of different part of the shoes](/assets/valtech/different-part.png)
*Image segmentation of different part of the shoes*

## Image generation

In the last weeks of my internship I worked on image generation using GANs. I used StyleGAN2 and SPADE to generate new shoes.

I first tried to use the trained M-RCNN model to generate segmentation map to do semantic generation. Each color was assigned a different class like background, sole, heel, etc.

![Semantic generation of shoes](/assets/valtech/spade.png)
*Semantic generation of a shoe, on the left the segmantation map as input and on the right the generated shoe*

Then I used the trained GAN model to generate new shoes.

![Example of generated shoes](/assets/valtech/stylegan.png)
*Example of generated shoes*

I trained StyleGan2 with ADA to increase the performance on limited data on our shoes dataset.

Finally using the trained StyleGan2 model I did some latent space exploration.

![Moving along the heel direction](/assets/valtech/interpolation.png)
*Moving along the heel direction for one shoe*

I generated some shoes and found their heel size using M-RCNN. Using that I was able to learn in the latent space the "heel direction". 

I was then able to move in this direction to reduce or increase the heel size of a shoe. I was then able to modify the aspect of a shoe.

## Technologies used

- [PyTorch](https://pytorch.org/)
- [fastai](https://docs.fast.ai/)
- [StyleGAN2](https://github.com/NVlabs/stylegan2-ada-pytorch)
- [labelbox](https://labelbox.com/)