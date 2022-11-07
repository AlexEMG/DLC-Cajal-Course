# Building your first DeepLabCut model

Let's build a DeepLabCut model!

## How to start? (15 min)

We highly recommend to read the [DeepLabCut Nature Protocol](https://rdcu.be/bHpHN) first, in particular Stages I-IX. See [below](#From-project-creation-to-training-your-model) for more details!

```{note}
You can either work on your own data, if you want to perform pose estimation or you can use [data that we provide!](DemoDatasets.md)
```

TODO_TA: Do you recommend some data? -- [check out the options](DemoDatasets.md) we suggest so far!


## What platform should you use? (5 min)

- use the graphical user interface (GUI)
- work in [COLAB notebooks](https://github.com/DeepLabCut/DeepLabCut/tree/master/examples#demo-jupyter--colaboratory-notebooks)
- or work in ipython

The TAs can introduce you to those different options as well as their merits.

## DeepLabCut's data model (10 min)

As we heard in the lecture, Machine Learning projects rely on training data and create neural network weights that you want to use for analyzing your data.

Thus, for a given project you want to have a `data structure` on your computer that keeps track of configuration files, training data and neural network weights. This is what DeepLabCut's data model addresses. A `project` is one folder (per project) that stores all those components in an organized fashion. A project directory has subdirectories: dlc-models, labeled-data, training-datasets, and videos.

You can even share these projects with others, and use them on different platforms. This comes in handy, as you may want to annotate with the GUI on your laptop, but then train your model on a computer with a GPU (or on COLAB). Once you have a useful model, you can also share the project with others, or just export the neural network weights!

So let's create our first project... and start labeling!

## Let's actually start...

Follow DeepLabCut's single animal workflow, [check DeepLabCut's documentation for details](https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html).

TODO_TA: What materials would you find helpful here? Shall we detail steps from the documentation also here? (or is it fine to refer to there, which I think makes more sense?)

## Creating a project and extracting frames (30 min)

## Labeling Frames (5 min - multiple hours)

## Check the quality! (5 min)

``deeplabcut.check_labels(config_path, visualizeindividuals=True/False)``

## Create a training dataset and pick model parameters

TODO_TA: [Here is an old demo video by me about networks](https://www.youtube.com/watch?v=ILsuC4icBU0&t=760s). Please check it out!

## Training your model (1h - longer)

TODO_TA: For your interactins with the students do you want tou use slides? E.g. this is a recent one I gave at JAX: <a href="https://github.com/DeepLabCut/DeepLabCut-Workshop-Materials/blob/master/JAX-TutorialOct2022.pdf?highlight=tutorial" target="_blank">link</a>


## Discussion topics

- What parameters should be picked?
    - for the most part the defaults are generalist parameters and will give you good performance
    - for some cases you can get better performance, which is best seen on videos/out-of-domain data. This is well illustrated in this [recipe for bats by Jonas Håkansson (one of our TAs)](https://deeplabcut.github.io/DeepLabCut/docs/recipes/flip_and_rotate.html).
    - You can also check out [Figure 8 in the Neuron Primer](https://www.cell.com/neuron/fulltext/S0896-6273(20)30717-0) and this [video](https://www.cell.com/cms/10.1016/j.neuron.2020.09.017/attachment/46e265f6-9ff2-4f64-9116-b8cc9c958fc4/mmc1), which compares different data augmentation methods on the same training set (this was also mentioned in the lecture today).
- How much data should you label?
- What should you consider when picking your neural network backbone?
-- Check out this [recipe](https://deeplabcut.github.io/DeepLabCut/docs/recipes/nn.html).

TODO_TA: What else?


Return to [readme](../README.md).
