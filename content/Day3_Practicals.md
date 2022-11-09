# Building on your first DeepLabCut model

We first want to tackle the general problem, of improving your DLC model. Mostly likely, especially because you're in the little data regime, you will get most bang for your buck by labeling the *right* frames, but augmentation, network architecture and hyperparameters will also help. So how can you find good frames to annotate?

```{note}
Alon Halevy, Peter Norvig, and Fernando Pereira from Google wrote the great piece: <a href="https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/35179.pdf" target="_blank">"The unreasonable effectiveness of data"</a>. It's a great read on how to learn good models for complex data...
```

## Active learning (How to improve yesterday's model)

For this part, we highly recommend to read  Stages X of <a href="https://rdcu.be/bHpHN" target="_blank">DeepLabCut Nature Protocol</a>.

If your model generalizes well to the type of data that you used yesterday that is great. But how can you make it more general and robust?

First, pick videos that are as different as possible (but still from your setup). Then create model predictions:

```
deeplabcut.analyze_videos(config_path,[‘Full path of video or videofolder’], shuffle=1, save_as_csv=True, videotype=‘.avi’)
```

And if the predictions are not as accurate as you want them, it is an ideal video for active learning. Check the different options for outlier extraction in the documentation and run:

```
deeplabcut.extract_outlier_frames(conﬁg_path,[‘videoﬁle_path’])
```

Once, you extracted outliers you can fix them manually:

```
deeplabcut.refine_labels(conﬁg_path,[‘videoﬁle_path’])
```

This will grow your dataset to better comprise the variablity. Then you can re-train your model. You can either train de-novo, or use the prior weights (which is faster and usually preferred).


## Discussion topics


TODO_TA: What else?


Return to [readme](../README.md).
