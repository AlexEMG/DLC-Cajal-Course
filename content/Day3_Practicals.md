# Building on your first DeepLabCut model

We first want to tackle the general problem, of improving your DLC model. Mostly likely, especially because you're in the little data regime, you will get most bang for your buck by labeling the *right* frames, but augmentation, network architecture and hyperparameters will also help. So how can you find good frames to annotate?

```{note}
Alon Halevy, Peter Norvig, and Fernando Pereira from Google wrote the great piece: <a href="https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/35179.pdf" target="_blank">"The unreasonable effectiveness of data"</a>. It's a great read on how to learn good models for complex data...
```

## Evaluation of yesterday's model

It is important to evaluate the performance of the trained network. This performance is measured by computing
the mean average Euclidean error (MAE; which is proportional to the average root mean square error) between the
manual labels and the ones predicted by DeepLabCut. The MAE is saved as a comma separated file and displayed
for all pairs and only likely pairs (>p-cutoff). This helps to exclude, for example, occluded body parts. One of the
strengths of DeepLabCut is that due to the probabilistic output of the scoremap, it can, if sufficiently trained, also
reliably report if a body part is visible in a given frame. (see discussions of finger tips in reaching and the Drosophila
legs during 3D behavior in [Mathis et al, 2018]). The evaluation results are computed by typing:
```python
deeplabcut.evaluate_network(config_path,Shuffles=[1], plotting=True)
```
Setting ``plotting`` to true plots all the testing and training frames with the manual and predicted labels. The user
should visually check the labeled test (and training) images that are created in the ‘evaluation-results’ directory.
Ideally, DeepLabCut labeled unseen (test images) according to the user’s required accuracy, and the average train
and test errors are comparable (good generalization). What (numerically) comprises an acceptable MAE depends on
many factors (including the size of the tracked body parts, the labeling variability, etc.). Note that the test error can
also be larger than the training error due to human variability (in labeling, see Figure 2 in Mathis et al, Nature Neuroscience 2018).


and thinking about peformance

- model comparison?
- overfitting (generalization gap etc.)
- how good could your model be? (limit is your accuracy) (link to recent DeepMind paper)
- how to improve your model



For video analysis you can also filter (maybe that is enough)
- show some examples of how filtering can really help

## Active learning (How to improve yesterday's model)

For this part, we highly recommend to read  Stages X of <a href="https://rdcu.be/bHpHN" target="_blank">DeepLabCut Nature Protocol</a>.

If your model generalizes well to the type of data that you used yesterday that is great. But how can you make it more general and robust?

First, pick videos that are as different as possible (but still from your setup). Then create model predictions:

```deeplabcut.analyze_videos(config_path,[‘Full path of video or videofolder’], shuffle=1, save_as_csv=True, videotype=‘.avi’)```

And if the predictions are not as accurate as you want them, it is an ideal video for active learning. Check the different options for outlier extraction in the documentation and run:

```deeplabcut.extract_outlier_frames(conﬁg_path,[‘videoﬁle_path’])```

Once, you extracted outliers you can fix them manually:

```deeplabcut.extract_refine_outliers(conﬁg_path,[‘videoﬁle_path’])```

This will grow your dataset to better comprise the variablity. Then you can re-train your model. You can either train de-novo, or use the prior weights (which is faster and usually preferred).


## Discussion topics



TODO_TA: What else?


Return to [readme](../README.md).
