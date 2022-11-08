# Lectures: ML and DLC

Firstly, if you never heard a lecture on Machine Learning (supervised and unsupervised learning) then we highly recommend you start with Part 1.

If, you are comfortable with the basics of Machine Learning, just skip ahead to [the introduction of computer vision and DeepLabCut](#part-2:-Introduction-to-Computer-Vision-and-DeepLabCut)

## Part 1: Introduction to Machine Learning (50 min)

```{note}
Art Samuel stated that Machine Learning "is the field of study that gives computers the ability to learn without being explicitly programmed."
```

[Introduction to Machine Learning by Eric Grimson](https://www.youtube.com/watch?v=h0e2HAPTGF4)
[![Intro to ML](http://img.youtube.com/vi/h0e2HAPTGF4/0.jpg)](https://www.youtube.com/watch?v=h0e2HAPTGF4 "Introduction to Machine Learning by Eric Grimson")

This lecture is part of an MIT class ---- [Introduction to Computational Thinking and Data Science, Fall 2016](http://ocw.mit.edu/6-0002F16)

Content of this lecture:
- What is machine learning? (minute 7+)
- Supervised & Unsupervised learning (minute 14+)
- Training & test performance (minute 48+)

```{figure} images/TraditionalProgrammingVSML_MIT.png
---
height: 200px
name: directive-fig
---
Traditional Programming vs. Machine Learning from Grimson's lecture.
```

Further reading (goes beyond this course, but recommended):
- [Part I of Deep Learning](https://www.deeplearningbook.org/) by Ian Goodfellow, Yoshua Bengio and Aaron Courville


TODO_TA: this doesn't cover neural networks + backprop. Shall we also recommend a lecture like: https://youtu.be/zUazLXZZA2U

## Part 2: Introduction to Computer Vision and DeepLabCut

Content:
- Basic computer vision intro
- Example supervised: ImageNet
- Pose estimation
- main results from Mathis et al. 2018
- [IID, OOD, Mathis et al. 2021](https://www.youtube.com/watch?v=pM6Z-ASiI2Y&t=104s). [Paper](https://openaccess.thecvf.com/content/WACV2021/html/Mathis_Pretraining_Boosts_Out-of-Domain_Robustness_for_Pose_Estimation_WACV_2021_paper.html)
- main challenges from a user perspective (how diverse data should be, augmentation)
- metrics: RMSE, test images
- ending with brief workflow of DLC (and software 2.0)

TODO_TA: Any other recommendations for content of this or prior class?
TODO_AM: record lecture.

As a stand-in for now, please check out:
[talk by AM at the CV4ecology Summer School at CalTech](https://www.youtube.com/watch?v=jfIb2qfAkQU)
[![DLC intro](http://img.youtube.com/vi/jfIb2qfAkQU/0.jpg)](https://www.youtube.com/watch?v=jfIb2qfAkQU "Introduction to DeepLabCut by Alexander Mathis")

(this contains also material that will be split in a different talk for day 3 and generally will be expanded for this audience)

Further reading (recommended in the scope of this course):
- Mathis, Schneider, Lauer, Mathis [A Primer on Motion Capture with Deep Learning: Principles, Pitfalls, and Perspectives](https://www.sciencedirect.com/science/article/pii/S0896627320307170), Neuron 2020

Further reading (goes beyond this course, but recommended):
- ImageNet paper
- ResNet paper
- [Part II of Deep Learning](https://www.deeplearningbook.org/) by Ian Goodfellow, Yoshua Bengio and Aaron Courville


Return to [readme](../README.md).
