# Demo Datasets

We provide several different datasets from small to large. Pick whatever you find most exciting!

# Single Animal Datasets (Day 2)

## Datasets with labels

### Small datasets (for playing)

- [mouse reaching dataset](https://github.com/DeepLabCut/DeepLabCut/tree/master/examples/Reaching-Mackenzie-2018-08-30) from Mathis et al. 2018, Nature Neuroscience.
- [mouse open-field dataset](https://github.com/DeepLabCut/DeepLabCut/tree/master/examples/openfield-Pranav-2018-10-30) comprising around 110 labeled images, subset of from Mathis et al. 2018, Nature Neuroscience. The full dataset can be found on [zenodo](https://zenodo.org/record/4008504#.Y2fE7uzMIeY).

You can simply load those datasets (and create a project) by running the following command:

```
deeplabcut.load_demo_data(config, createtrainingset=False)
```
Where you pass the path to the config file of interest as `config`.

### Big datasets

- [Horse10](http://www.mackenziemathislab.org/horse10) contains >8,000 expertly labeled frames across 30 individual thoroughbred horses.


## Datasets without labels

TODO_DK: put link to suggested videos

# Multi Animal Datasets (Day 3)

- [Mont-Blanc bird dataset](https://github.com/DeepLabCut/DeepLabCut_maDLC_DemoData) contains a small dataset of multiple birds.




TODO_AM: link to https://deeplabcut.github.io/DeepLabCut/docs/HelperFunctions.html#model-export-function

TODO_AM: put dataset in standard docs
