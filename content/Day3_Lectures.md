# Lectures

First, let's assume you have a model that is great for analyzing your data. In that case, you can 1️⃣ extend it to a multianimal project if applicable (**maDeepLabCut**), 2️⃣ share it with the community (**Model Zoo**), 3️⃣ use it in closed-loop behavior experiments (**DeepLabCut-live**), or 4️⃣ integrate it with other camera views for 3D pose estimation (**3D DeepLabCut**).

## Part 1: maDeepLabCut (⏳30 min)

- (Additional) challenges for multi-individual pose estimation (vs. single animal)
- Bottom-up vs. Top-down methods 🔼🔽
- Check this paper {cite}`Lauer2022` and how maDLC works
- supervised and unsupervised identification of indivudals
- Tracking
- Metrics 📐 for multi-individual pose est. mAP, MOTA, etc.

TODO_AM: record lecture.

As a stand-in for now, please check out minutes 30-42
[talk by AM at the CV4ecology Summer School at CalTech](https://www.youtube.com/watch?v=jfIb2qfAkQU)
[![DLC intro](http://img.youtube.com/vi/jfIb2qfAkQU/0.jpg)](https://www.youtube.com/watch?v=jfIb2qfAkQU "Introduction to DeepLabCut by Alexander Mathis")


## Part 4: Model Zoo (⏳15 min)

- Model Zoos in Deep Learning Frameworks
- This is larger scale transfer learning than prior
- DLC Super Models, Ye et al.
- How to train 🚂 models on supersets of data
- Zero-shot performance, catastrophic forgetting and ways to overcome it
- How to contribute data + labels 🙏 - https://contrib.deeplabcut.org
- How to use models - https://contrib.deeplabcut.org
- Open Challenges 🔥 for OOD generalization

TODO_AM: record lecture

As a stand-in for now, please check out minutes 48+
[talk by AM at the CV4ecology Summer School at CalTech](https://www.youtube.com/watch?v=jfIb2qfAkQU)
[![DLC intro](http://img.youtube.com/vi/jfIb2qfAkQU/0.jpg)](https://www.youtube.com/watch?v=jfIb2qfAkQU "Introduction to DeepLabCut by Alexander Mathis")


## Part 1: DeepLabCut-live (⏳15 min)

DeepLabCut provides additional software packages that allow you to record and stream camera data and run DeeplabCut models in real-time. You can get a quick overview by watching this short [clip](https://www.youtube.com/watch?v=KDSgddOqHtM).

For more details, please watch 👀 Gary Kane's [DLC-live Neuromatch talk](https://www.youtube.com/watch?v=cwOTdxpU2_4). This recording also contains questions from the audience, so you can stop after minute 7.

For more information on this work, please check out {cite}`Kane2020` 


- put more stuff 📦 on benchmarking
- update to Goal ⚽️ for the end of the day


TODO_TA: Any other recommendations for content for this module?

## Part 2: 3D DeepLabCut (⏳15 min)

Content:
- 3D pose estimation
- Monocular vs. multi-view
- Nath, Joska publications (Kalman filter, )
- camera calibration, triangulation
- Anipose and other tools
- metrics for 3D pose estimation (MPJE)
- learning vs. optimization
- recipe for how to do in DLC
- more challenging

TODO_AM: record lecture.

As a stand-in for now, please check out minutes 19 - 21
[talk by AM at the CV4ecology Summer School at CalTech](https://www.youtube.com/watch?v=jfIb2qfAkQU)
[![DLC intro](http://img.youtube.com/vi/jfIb2qfAkQU/0.jpg)](https://www.youtube.com/watch?v=jfIb2qfAkQU "Introduction to DeepLabCut by Alexander Mathis")

#References

```{bibliography}
:filter: docname in docnames
```

[Let’s go back 🔙](../README.md).
