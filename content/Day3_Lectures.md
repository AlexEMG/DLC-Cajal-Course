# Lectures

Today we have lectures on several topics -->  1️⃣ how to track multiple animals with DeepLabCut (**maDeepLabCut**), 2️⃣ how to share models with the community and how we create SuperModels (**Model Zoo**), 3️⃣ how to use DeepLabCut in closed-loop behavior experiments (**DeepLabCut-live**), as well as 4️⃣ how to integrate it with other camera views for 3D pose estimation (**3D DeepLabCut**).

## Part 1: maDeepLabCut (⏳30 min)

TODO_AM: link lecture.

For further information, check out: {cite}`Lauer2022`.

## Part 2: Model Zoo (⏳12 min)

[DeepLabCut Model Zoo by Prof. Mackenzie Mathis](https://youtu.be/miI64k6EnMM)
[![DLC intro](http://img.youtube.com/vi/miI64k6EnMM/0.jpg)](https://www.youtube.com/watch?v=miI64k6EnMM "DeepLabCut Model Zoo by Prof. Mackenzie Mathis")

For further information, check out: {cite}`ye2022panoptic`.

Further reading (recommended in the scope of this course):
- How to contribute data + labels 🙏 - https://contrib.deeplabcut.org
- How to use models: <a href="http://www.mackenziemathislab.org/dlc-modelzoo" target="_blank">browse available models</a>.

## Part 3: DeepLabCut-live (⏳15 min)

DeepLabCut provides additional software packages that allow you to record and stream camera data and run DeeplabCut models in real-time. You can get a quick overview by watching this short [clip](https://www.youtube.com/watch?v=KDSgddOqHtM).

For more details, please watch 👀 Gary Kane's [DLC-live Neuromatch talk](https://www.youtube.com/watch?v=cwOTdxpU2_4). This recording also contains questions from the audience, so you can stop after minute 7.

For more information on this work, please check out {cite}`Kane2020`. Regarding inference speeds, please also check out the [DLC Inference Speed Benchmark](https://deeplabcut.github.io/DLC-inferencespeed-benchmark/). You can also contribute inference speeds for additional hardware [here](https://github.com/DeepLabCut/DLC-inferencespeed-benchmark), plus check out {cite}`Kane2020` for more details.

DLC-live also provides a convenient API for combining animal pose estimation with other tasks. For example, DLC-live was used here in combination with MegaDetector to estimate the pose of animals detected in camera trap data. You can see a demo which also uses the Model Zoo [here](https://huggingface.co/spaces/DeepLabCut/MegaDetector_DeepLabCut) and inspect the code further [here](https://huggingface.co/spaces/DeepLabCut/MegaDetector_DeepLabCut/tree/main).


## Part 4: 3D DeepLabCut (⏳15 min)

TODO_AM: link lecture.

For further information, check out: {cite}`Nath2019`, {cite}`Joska2021`, {cite}`wang2021deep`.

If you want to expand your knowledge, check out these materials:
- [Review on 3D pose estimation](https://www.sciencedirect.com/science/article/pii/S2096579620300887)
- Excellent textbook on [Multiple View Geometry in Computer Vision
](https://www.robots.ox.ac.uk/~vgg/hzbook/hzbook2/HZfigures.html) by Richard Hartley and Andrew Zisserman


# References

```{bibliography}
:filter: docname in docnames
```

[Let’s go back 🔙](../README.md).
