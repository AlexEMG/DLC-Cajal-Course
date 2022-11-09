# Creating your multi-animal pose tracker

### Multi-animal pose tracking workflow

The workflow for multi-animal DeepLabCut is a bit more complicated. You should think of maDLC requiring four parts:

(1) Curate annotation data that allows you to learn a model to track the objects/animals of interest.
(2) Create a high-quality pose estimation model (this is like the single-animal case)
(3) Track in space and time, i.e., assemble bodyparts to detect objects/animals and link across time. This step performs assembly and tracking (comprising first local tracking and then tracklet stitching by global reasoning).
(4) Any and all post-processing you wish to do with the output data, either within DLC or outside of it.
Thus, you should always label, train, and evaluate the pose estimation performance first. If and when that performance is high, then you should go advance to the tracking step (and video analysis). There is a natural break point for this, as you will see below.

<img src="https://images.squarespace-cdn.com/content/v1/57f6d51c9f74566f55ecf271/1596370260800-SP2GWKDPJCOIR7LJ31VM/ke17ZwdGBToddI8pDm48kB4fL2ovSQh5dRlH2jCMtpoUqsxRUqqbr1mOJYKfIPR7LoDQ9mXPOjoJoqy81S2I8N_N4V1vUb5AoIIIbLZhVYxCRW4BPu10St3TBAUQYVKcSV94BuD0XUinmig_1P1RJNYVU597j3jgswapL4c_w92BJE9r6UgUperYhWQ2ubQ_/workflow.png?format=2500w" width="550" title="maDLC" alt="maDLC" align="center" vspace = "50">

TODO_TA: What else should we put here?

For detailed information on the different steps in the workflow, please refer to the multi-animal user guide: <a href="https://deeplabcut.github.io/DeepLabCut/docs/maDLC_UserGuide.html#multi-animal-userguide" target="_blank">maDLC user guide</a>.

## GUI:

Full graphical user interface: just follow the tabs in the GUI, use `python -m deeplabcut` to launch the GUI.

### COLAB

<a href="https://github.com/DeepLabCut/DeepLabCut/blob/master/examples/COLAB/COLAB_transformer_reID.ipynb" target="_blank">DeepLabCut 2.2 Toolbox Demo on how to use our Pose Transformer for unsupervised identity tracking of animals</a>

## Python commands:

**Import deeplabcut**
```python
import deeplabcut
```

**(1) Create a project**
```python
project_name = "cutemice"
experimenter = "teamdlc"
video_path = "path_to_a_video_file"
config_path = deeplabcut.create_new_project(
    project_name,
    experimenter,
    [video_paths],
    multianimal=True,
    copy_videos=True,
)
```
> **_NOTE:_**  Make sure to specify the absolute path to the video file(s).
> It is quickly obtained on Windows with <kbd>⇧ Shift</kbd>+<kbd>Right click</kbd> and `Copy as path`,
> and on Mac with <kbd>⌥ Option</kbd>+<kbd>Right click</kbd> and `Copy as Pathname`.
> Ubuntu users only need to copy the file and its path gets added to the clipboard.

> Next, you can set a variable for the config_path: 'Full path of the project configuration file*'

**(2) Edit the config.ymal file to set up your project**
> **_NOTE:_** Here is were you will define your key point names and animal IDs. Also you can change the default # of frames to extract for the next step.

**(3) Extract video frames to annotate**
```python
deeplabcut.extract_frames(
    config_path,
    mode="automatic",
    algo="kmeans",
    userfeedback=False,
)
```
> **_NOTE:_** try to extract a few frames from many videos vs. a lot of frames from one video!

**(4) Annotate Frames**
```python
deeplabcut.label_frames(config_path)
```


**(5) Visually check annotated frames**
```python
deeplabcut.check_labels(
    config_path,
    draw_skeleton=False,
)
```

**(6) Create the training dataset**
```python
deeplabcut.create_multianimaltraining_dataset(
    config_path,
    num_shuffles=1,
    net_type="dlcrnet_ms5",
)
```

**(7) Train the network**
```python
deeplabcut.train_network(
    config_path,
    saveiters=10000,
    maxiters=50000,
    allow_growth=True,
)
```

**(8) Evaluate the network**
```python
deeplabcut.evaluate_network(
    config_path,
    plotting=True,
)
```

**(9) Analyze a video (extracts detections and association costs)**
```python
deeplabcut.analyze_videos(
    config_path,
    [video],
    auto_track=True,
)
```
> **_NOTE:_** `auto_track=True` will complete steps 10-11 for you automatically so you get the "final" H5 file. Use the below steps if you need to change the parameters of tracking based on your dataset.


**(10) Spatial and (locally) temporal grouping: Track body part assemblies frame-by-frame**
```python
deeplabcut.convert_detections2tracklets(
    config_path,
    [video],
    track_method="ellipse",
)
```


**(11) Reconstruct full animal trajectories (tracks from tracklets)**
```python
deeplabcut.stitch_tracklets(
    config_path,
    [video],
    track_method="ellipse",
    min_length=5,
)
```


**(12) Create a pretty video output**
```python
deeplabcut.create_labeled_video(
    config_path,
    [video],
    color_by="individual",
    keypoints_only=False,
    trailpoints=10,
    draw_skeleton=False,
    track_method="ellipse",
)
```

TODO_TA: What else?

TODO_AM: expand critical points and link to maDLC user guide!

Return to [readme](../README.md).
