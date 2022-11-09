# Building your first DeepLabCut model

Let's build a DeepLabCut model!

## How to start? (15 min)

We highly recommend to read the [DeepLabCut Nature Protocol](https://rdcu.be/bHpHN) first, in particular Stages I-IX. See [below](#From-project-creation-to-training-your-model) for more details. The figure below visualize the workflow of DeepLabCut:

 <p align="center">
<img src="https://static1.squarespace.com/static/57f6d51c9f74566f55ecf271/t/5cca272524a69435c3251c40/1556752170424/flowfig.jpg?format=1000w" height="400">

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

The following summarises DeepLabCut's single animal workflow. If your dataset involves multiple animals that look the same, please consult the <a href="https://deeplabcut.github.io/DeepLabCut/docs/maDLC_UserGuide.html#multi-animal-userguide" target="_blank">maDLC user guide</a> (however, be warned the workflow is more involved, as it adds additional steps; for educational purposes you could focus on a single animal project first, if you have never used DeepLabCut).

If you wish to use the Project Manager GUI (recommended for beginners), you can check out <a href="https://deeplabcut.github.io/DeepLabCut/docs/PROJECT_GUI.html" target="_blank">this guidance and video demos</a>.

TODO_TA: What materials would you find helpful here? Shall we detail steps from the documentation also here? (or is it fine to refer to there, which I think makes more sense?)

## Creating a project and extracting frames (30 min)

The function `create_new_project` creates a new project directory, required subdirectories, and a basic project configuration file. Check <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#a-create-a-new-project" target="_blank">DeepLabCut's documentation</a> for details.

<pre lang="python">deeplabcut.create_new_project('Name of the project', 'Name of the experimenter', ['Full path of video 1', 'Full path of video2', 'Full path of video3'], working_directory='Full path of the working directory', copy_videos=True/False, multianimal=True/False)</pre>

Next, open the **config.yaml** file from your project directory. Familiarise yourself with the <a href="https://static1.squarespace.com/static/57f6d51c9f74566f55ecf271/t/5c40f4124d7a9c0b2ce651c1/1547760716298/Box1-01.png?format=1000w" target="_blank">meaning of the parameters</a>. You **must add the list of bodyparts (or points of interest)** that you want to track. Do not have spaces in the names of bodyparts!

The function `extract_frames` extracts frames from all the videos in the project configuration file in order to create a training dataset. Have a look at <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#c-data-selection-extract-frames" target="_blank">the DeepLabCut documentation</a> to decide:
- how many frames to extract,
- how to choose the frame extraction method that best suits your data,
- how to control which videos to extract frames from,
- whether to crop videos.

<pre lang="python">deeplabcut.extract_frames(config_path, mode='automatic/manual', algo='uniform/kmeans', userfeedback=False, crop=True/False)</pre>

## Labeling Frames (5 min - multiple hours)
The function `label_frames` helps the user easily label all the extracted frames using an interactive graphical user interface (GUI). Check <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#d-label-frames" target="_blank">the documentation</a> for pointers on how to use GUI.

<pre lang="python">deeplabcut.label_frames(config_path)</pre>

## Check the quality! (5 min)
The function `check_labels` allows the user to check if the labels were created and stored correctly. For more information, including on what to do if you discover labeling errors, check the <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#e-check-annotated-frames" target="_blank">DLC docs</a>!

<pre lang="python">deeplabcut.check_labels(config_path, visualizeindividuals=True/False)</pre>

## Create a training dataset and pick model parameters
You should continue on the machine/platform **where** you are going to train the network. You might have to edit your configuration file, so read <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#f-create-training-dataset-s" target="_blank">the DeepLabCut documentation</a> carefully to make sure you are ready to proceed.

The function `create_training_dataset` combines the labeled datasets from all the videos and splits them to create train and test datasets. Check <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#f-create-training-dataset-s" target="_blank">the documentation</a> to learn how to choose the most suitable pre-trained network and data augmentation method for your project.

TODO_TA: [Here is an old demo video by me about networks](https://www.youtube.com/watch?v=ILsuC4icBU0&t=760s). Please check it out!

## Training your model (1h - longer)
The function `train_network` helps the user in training the network, using the parameters set in the **pose_cfg.yaml** file. Familiarise yourself with <a href="https://images.squarespace-cdn.com/content/v1/57f6d51c9f74566f55ecf271/1570325287859-NHCTKWOFWPVWLH8B79PS/ke17ZwdGBToddI8pDm48kApwhYXjNb7J-ZG10ZuuPUJ7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0uRNgJXBmK_J7vOfsoUyYccR03UZyExumRKzyR7hPRvjPGikK2uEIM-3GOD5thTJoQ/Box2-01.png?format=1000w" target="_blank">the meaning of those parameters</a> and check <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#g-train-the-network" target="_blank">the DLC documentation</a> to learn:
- how many iterations to train your model for,
- how often to store weights and display loss,
- how to restart training at a specific checkpoint.

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
