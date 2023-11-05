# Training 🏋️‍♀️ your first DeepLabCut model

Let's build our first DeepLabCut model ✨!

## How to start? (⏳15 min)

We highly recommend you to read this Protocol first {cite}`Nath2019`. Especially, Stages I-IX.  In the figure below you can see the workflow of DeepLabCut :

 <p align="center">
<img src="https://static1.squarespace.com/static/57f6d51c9f74566f55ecf271/t/5cca272524a69435c3251c40/1556752170424/flowfig.jpg?format=1000w" height="400">

```{note}
You can either work on your own data, if you want to perform pose estimation or you can use [one of the demo datasets](DemoDatasets.md).
```

## Think about your options and preferences (⏳5 min)

The TAs can introduce you to a few different options as well as their merits.

- Do you plan to run DLC on the CPU or do you have access to GPUs?
    - Training and evaluating DLC models on the CPU will be much slower, but it can be useful to test things locally
    - There are a few options to use GPUs for training and inference:
        - You may have a decent GPU in your laptop 💻, or
        - You may have access to a workstation 🚧 in the lab with GPUs, or
        - You may consider using GPUs in the cloud, for example with a [Colab notebook](https://github.com/DeepLabCut/DeepLabCut/tree/master/examples#demo-jupyter--colaboratory-notebooks)

- Are you comfortable with Python 🐍 scripting or would you prefer to use the GUI?
    - The [DLC GUI](https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#deeplabcut-project-manager-gui-recommended-for-beginners) provides a user-friendly interface that guides you through the model building process
    - Alternatively you can the Python API, which provides high-level well-documented Python functions for each of the model building steps
        - You can use Python scripting interactively in the Terminal (via `ipython`), or you can use them to write your own script
        - If you plan to use GPU power via the [Colab notebook](https://github.com/DeepLabCut/DeepLabCut/tree/master/examples#demo-jupyter--colaboratory-notebooks), you will need to use the Python API
        - See [DeepLabCut in the Terminal](https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#deeplabcut-in-the-terminal) for a step-by-step guide 🗺

## DeepLabCut's data model (⏳10 min)

Machine Learning projects rely on training data and create neural network weights that you want to use for analyzing your data.

Thus, for a given project you want to have a `data structure` on your computer that keeps track of configuration files, training data and neural network weights. This is what DeepLabCut's data model addresses. A `project` is one folder 📂 (per project) that stores all those components in an organized fashion. A project directory has subdirectories: dlc-models, labeled-data, training-datasets, and videos.

You can even share these projects with others, and use them on different platforms. This comes in handy, as you may want to annotate with the GUI on your laptop, but then train 🏋️‍♀️ your model on a computer with a GPU (or on COLAB). Once you have a useful model, you can also share the project with others, or just export the neural network weights!

So let's create our first project... and start labeling 🎉🎉!

## 🔥 Let's start...

The following summarises DeepLabCut's single animal workflow. If your dataset involves multiple animals that look the same, please consult the <a href="https://deeplabcut.github.io/DeepLabCut/docs/maDLC_UserGuide.html#multi-animal-userguide" target="_blank">maDLC user guide</a> (however, be warned the workflow is more involved, as it adds additional steps; for educational purposes you could focus on a single animal project first, if you have never used DeepLabCut).

If you wish to use the Project Manager GUI (recommended for beginners), you can check out <a href="https://deeplabcut.github.io/DeepLabCut/docs/PROJECT_GUI.html" target="_blank">this guidance and video demos</a>.

## Creating a project and extracting frames (⏳30 min)

The function `create_new_project` creates a new project directory, required subdirectories, and a basic project configuration file. Check <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#a-create-a-new-project" target="_blank">DeepLabCut's documentation</a> for details.

<pre lang="python">deeplabcut.create_new_project('Name of the project', 'Name of the experimenter', ['Full path of video 1', 'Full path of video2', 'Full path of video3'], working_directory='Full path of the working directory', copy_videos=True/False, multianimal=True/False)</pre>

[GUI project creation](https://youtu.be/KcXogR-p5Ak?t=32)

Next, open the **config.yaml** file from your project directory. Familiarise yourself with the <a href="https://static1.squarespace.com/static/57f6d51c9f74566f55ecf271/t/5c40f4124d7a9c0b2ce651c1/1547760716298/Box1-01.png?format=1000w" target="_blank">meaning of the parameters</a>. You **must add the list of bodyparts (or points of interest)** that you want to track. Do not have spaces in the names of bodyparts!

The function `extract_frames` extracts frames from all the videos in the project configuration file in order to create a training dataset. Have a look at the <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#c-data-selection-extract-frames" target="_blank">DeepLabCut documentation</a> to decide:
- how many frames to extract,
- how to choose the frame extraction method that best suits your data,
- how to control which videos to extract frames from,
- whether to crop videos.

<pre lang="python">deeplabcut.extract_frames(config_path, mode='automatic/manual', algo='uniform/kmeans', userfeedback=False, crop=True/False)</pre>

[GUI frame extraction](https://youtu.be/KcXogR-p5Ak?t=87)

## Labeling Frames (⏳5 min - multiple hours)
The function `label_frames` helps the user easily label all the extracted frames using an interactive graphical user interface (GUI). Check <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#d-label-frames" target="_blank">the documentation</a> for pointers on how to use GUI.

<pre lang="python">deeplabcut.label_frames(config_path)</pre>

[GUI frame labelling](https://youtu.be/KcXogR-p5Ak?t=111)

## Check the quality! (⏳5 min)
The function `check_labels` allows the user to check if the labels were created and stored correctly. For more information, including on what to do if you discover labeling errors, check the <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#e-check-annotated-frames" target="_blank">DLC docs</a>!

<pre lang="python">deeplabcut.check_labels(config_path, visualizeindividuals=True/False)</pre>

## Create a training dataset and pick model parameters
You should continue on the machine/platform **where** you are going to train the network. You might have to edit your configuration file, so read <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#f-create-training-dataset-s" target="_blank">the DeepLabCut documentation</a> carefully to make sure you are ready to proceed.

[GUI creating training dataset](https://youtu.be/KcXogR-p5Ak?t=160)

The function `create_training_dataset` combines the labeled datasets from all the videos and splits them to create train and test datasets. Check <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#f-create-training-dataset-s" target="_blank">the documentation</a> to learn how to choose the most suitable pre-trained network and data augmentation method for your project.

## Training your model (⏳1h - longer)
The function `train_network` helps the user in training the network, using the parameters set in the **pose_cfg.yaml** file. Familiarise yourself with <a href="https://images.squarespace-cdn.com/content/v1/57f6d51c9f74566f55ecf271/1570325287859-NHCTKWOFWPVWLH8B79PS/ke17ZwdGBToddI8pDm48kApwhYXjNb7J-ZG10ZuuPUJ7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0uRNgJXBmK_J7vOfsoUyYccR03UZyExumRKzyR7hPRvjPGikK2uEIM-3GOD5thTJoQ/Box2-01.png?format=1000w" target="_blank">the meaning of those parameters</a> and check <a href="https://deeplabcut.github.io/DeepLabCut/docs/standardDeepLabCut_UserGuide.html#g-train-the-network" target="_blank">the DLC documentation</a> to learn:
- how many iterations to train your model for,
- how often to store weights and display loss,
- how to restart training at a specific checkpoint.

[GUI train network](https://youtu.be/WXCVr6xAcCA?t=58)

## Let’s Talk 📲

- What parameters should be picked?
    - for the most part the defaults are generalist parameters and will give you good performance
    - for some cases you can get better performance, which is best seen on videos/out-of-domain data. This is well illustrated in this [recipe for bats by Jonas Håkansson (one of our TAs)](https://deeplabcut.github.io/DeepLabCut/docs/recipes/flip_and_rotate.html).
    - You can also check out [Figure 8 in the Neuron Primer](https://www.cell.com/neuron/fulltext/S0896-6273(20)30717-0) and this [video](https://www.cell.com/cms/10.1016/j.neuron.2020.09.017/attachment/46e265f6-9ff2-4f64-9116-b8cc9c958fc4/mmc1), which compares different data augmentation methods on the same training set (this was also mentioned in the lecture today).
- How much data should you label?
- What should you consider when picking your neural network backbone?
-- Check out this [recipe](https://deeplabcut.github.io/DeepLabCut/docs/recipes/nn.html).


````{admonition} References
:class: seealso
```{bibliography}
:filter: docname in docnames
```
````

[Let’s go back 🔙](../README.md).
