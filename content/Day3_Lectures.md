# Lectures

Today we have lectures on several topics -->  1️⃣ how to track multiple animals with DeepLabCut (**maDeepLabCut**), 2️⃣ how to share models with the community and how we create SuperModels (**Model Zoo**), 3️⃣ how to use DeepLabCut in closed-loop behavior experiments (**DeepLabCut-live**), as well as 4️⃣ how to integrate it with other camera views for 3D pose estimation (**3D DeepLabCut**).

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


## Part 2: Model Zoo (⏳12 min)

[DeepLabCut Model Zoo by Prof. Mackenzie Mathis](https://youtu.be/miI64k6EnMM)
[![DLC intro](http://img.youtube.com/vi/miI64k6EnMM/0.jpg)](https://www.youtube.com/watch?v=miI64k6EnMM "DeepLabCut Model Zoo by Prof. Mackenzie Mathis")

Further reading (recommended in the scope of this course):
- How to contribute data + labels 🙏 - https://contrib.deeplabcut.org
- How to use models: <a href="http://www.mackenziemathislab.org/dlc-modelzoo" target="_blank">browse available models</a>.

## Part 3: DeepLabCut-live (⏳15 min)

DeepLabCut provides additional software packages that allow you to record and stream camera data and run DeeplabCut models in real-time. You can get a quick overview by watching this short [clip](https://www.youtube.com/watch?v=KDSgddOqHtM).

For more details, please watch 👀 Gary Kane's [DLC-live Neuromatch talk](https://www.youtube.com/watch?v=cwOTdxpU2_4). This recording also contains questions from the audience, so you can stop after minute 7.

For more information on this work, please check out {cite}`Kane2020`

- put more stuff 📦 on benchmarking
- update to Goal ⚽️ for the end of the day

DLC-live also provides a convenient API for combining animal pose estimation with other tasks. For example, DLC-live was used here in combination with MegaDetector to estimate the pose of animals detected in camera trap data. You can see a demo which also uses the Model Zoo [here](https://huggingface.co/spaces/DeepLabCut/MegaDetector_DeepLabCut) and inspect the code further [here](https://huggingface.co/spaces/DeepLabCut/MegaDetector_DeepLabCut/tree/main).

TODO_TA: Any other recommendations for content for this module?

## Part 4: 3D DeepLabCut (⏳15 min)

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
