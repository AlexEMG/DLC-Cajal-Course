# Building on your first DeepLabCut model

We first want to tackle the general problem, of improving your DLC model. Mostly likely, especially because you're in the little data regime, you will get most bang for your buck by labeling the *right* frames, but augmentation, network architecture and hyperparameters will also help. So how can you find good frames to annotate?

```{note}
Alon Halevy, Peter Norvig, and Fernando Pereira from Google wrote the great piece: <a href="https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/35179.pdf" target="_blank">"The unreasonable effectiveness of data"</a>. It's a great read on how to learn good models for complex data...
```

## Active learning (How to improve yesterday's model)

For this part, we highly recommend to read  Stages X of <a href="https://rdcu.be/bHpHN" target="_blank">DeepLabCut Nature Protocol</a>.

If your model generalizes well to the type of data that you used yesterday that is great. But how can you make it more general and robust?

First, pick videos that are as different as possible (but still from your setup). Then create model predictions:

```deeplabcut.analyze_videos(config_path,[‘Full path of video or videofolder’], shuffle=1, save_as_csv=True, videotype=‘.avi’)```

And if the predictions are not as accurate as you want them, it is an ideal video for active learning. Check the different options for outlier extraction in the documentation and run:

```deeplabcut.extract_outlier_frames(conﬁg_path,[‘videoﬁle_path’])```

Once, you extracted outliers you can fix them manually:

```deeplabcut.extract_outlier_frames(conﬁg_path,[‘videoﬁle_path’])```

This will grow your dataset to better comprise the variablity. Then you can re-train your model. You can either train de-novo, or use the prior weights (which is faster and usually preferred).

## Using the DeepLabCut Model Zoo

First, you can record a video of other students or your cat/dog!

Then you can analyze it using this notebook:
<a href="https://github.com/DeepLabCut/DeepLabCut/blob/master/examples/COLAB/COLAB_DLC_ModelZoo.ipynb" target="_blank">DeepLabCut Model Zoo Colab Notebook</a>

```{note}
Validate how it important it is to match the relative size of the individuals in the video.
```

## DLC-live

- How to do an online experiment?

## Multi-animal pose stimation

### Multi-animal pose tracking workflow

The workflow for multi-animal DeepLabCut is a bit more complicated. You should think of maDLC requiring four parts:

(1) Curate annotation data that allows you to learn a model to track the objects/animals of interest.
(2) Create a high-quality pose estimation model (this is like the single-animal case)
(3) Track in space and time, i.e., assemble bodyparts to detected objects/animals and link across time. This step performs assembly and tracking (comprising first local tracking and then tracklet stitching by global reasoning).
(4) Any and all post-processing you wish to do with the output data, either within DLC or outside of it.
Thus, you should always label, train, and evaluate the pose estimation performance first. If and when that performance is high, then you should go advance to the tracking step (and video analysis). There is a natural break point for this, as you will see below.

<img src="https://images.squarespace-cdn.com/content/v1/57f6d51c9f74566f55ecf271/1596370260800-SP2GWKDPJCOIR7LJ31VM/ke17ZwdGBToddI8pDm48kB4fL2ovSQh5dRlH2jCMtpoUqsxRUqqbr1mOJYKfIPR7LoDQ9mXPOjoJoqy81S2I8N_N4V1vUb5AoIIIbLZhVYxCRW4BPu10St3TBAUQYVKcSV94BuD0XUinmig_1P1RJNYVU597j3jgswapL4c_w92BJE9r6UgUperYhWQ2ubQ_/workflow.png?format=2500w" width="550" title="maDLC" alt="maDLC" align="center" vspace = "50">

TODO_TA: What else?

https://deeplabcut.github.io/DeepLabCut/docs/tutorial.html

### Utilizing unsupervised ReID for improving tracking

<a href="https://github.com/DeepLabCut/DeepLabCut/blob/master/examples/COLAB/COLAB_transformer_reID.ipynb" target="_blank">DeepLabCut 2.2 Toolbox Demo on how to use our Pose Transformer for unsupervised identity tracking of animals</a>


## Discussion topics

-

TODO_TA: What else?


Return to [readme](../README.md).
