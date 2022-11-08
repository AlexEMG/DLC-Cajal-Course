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
- [Chapter 1 of Deep Learning](https://www.deeplearningbook.org/) by Ian Goodfellow, Yoshua Bengio and Aaron Courville
- [The basics of neural networks, and the math behind how they learn](https://www.3blue1brown.com/topics/neural-networks) by 3Blue1Brown
- [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/index.html) by Michael Nielsen
- [Understanding Mini-Batch Gradient Descent](https://www.youtube.com/watch?v=-_4Zi8fCZO4) by Andrew Ng (DeepLearningAI)

TODO_TA: this doesn't cover neural networks + backprop. Shall we also recommend a lecture like: https://youtu.be/zUazLXZZA2U
- I think a brief clarification of differences between ML, DL, AI (and maybe computer vision?) could be useful in this section. Maybe just simply adding/referring to the Figure 1.4 in [Deep Learning book](https://www.deeplearningbook.org/) 

## Part 2: Introduction to Computer Vision and DeepLabCut

Content:
- Basic computer vision intro
- Example supervised: ImageNet
- Pose estimation
- main results from Mathis et al. 2018
- [IID, OOD, Mathis et al. 2021](https://www.youtube.com/watch?v=pM6Z-ASiI2Y&t=104s). [Paper](https://openaccess.thecvf.com/content/WACV2021/html/Mathis_Pretraining_Boosts_Out-of-Domain_Robustness_for_Pose_Estimation_WACV_2021_paper.html)
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

Further content for reading and watching (goes beyond this course, but recommended):
- [Brief history of vision and computer vision](https://www.youtube.com/watch?v=vT1JzLTH4G4&t=855s) by Fei-Fei Li
- ResNet paper
- [Part II of Deep Learning](https://www.deeplearningbook.org/) by Ian Goodfellow, Yoshua Bengio and Aaron Courville
- [Lecture collection to deep dive into details of the deep learning architectures from Stanford University](https://www.youtube.com/playlist?list=PL3FW7Lu3i5JvHM8ljYj-zLfQRF3EO8sYv)

Return to [readme](../README.md).
