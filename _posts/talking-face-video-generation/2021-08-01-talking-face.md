---
layout: post
title: Talking Face Video Generation using Deep Learning
date: 2021-08-01 01:00 +0700
description: This was a research internship at INRIA. I was working on talking face video generation using GANs. 
tag:
  - deep learning
  - computer vision
---

I had the opportunity to do a research internship at INRIA, a french research institute. I was working on talking face video generation using GANs and CNNs.

![Talking Face Generation example](/assets/talking-face/talking-face.gif)

*Video puppeteering, on the left the driving video and on the right the generated video*

I wrote an article where I summarized state-of-the-art research in video generation. I then compared them on the same data. When the code wasn't available I reimplemented the code or part of the code in PyTorch.

You can find the article [here](https://wandb.ai/rntc/latent-pose-reenactment/reports/Talking-Face-Generation--Vmlldzo3MDM5NzI).

I then implemented a new archtitecture based on CNNs and a GAN developed at INRIA. Unfortunately, I didn't have the time to test it.

You can find the code [on github here](https://github.com/Rian-T/AudioDrivenTalkingHeadGeneration).

I also collected a new audio-video dataset using selenium that I automatically cropped around the face.

## Technologies used

- [PyTorch](https://pytorch.org/)
- [PyTorch Lightning](https://pytorch-lightning.readthedocs.io/)
- [ffmpeg](https://www.ffmpeg.org/)