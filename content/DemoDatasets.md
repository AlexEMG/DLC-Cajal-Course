# Demo Datasets

We provide several different datasets from small to large. Pick whatever you find most exciting!

# Single Animal Datasets (Day 2)

## Datasets with labels

### Small datasets (for playing)

- [mouse reaching dataset](https://github.com/DeepLabCut/DeepLabCut/tree/master/examples/Reaching-Mackenzie-2018-08-30) from Mathis et al. 2018, Nature Neuroscience.
- [mouse open-field dataset](https://github.com/DeepLabCut/DeepLabCut/tree/master/examples/openfield-Pranav-2018-10-30) comprising around 110 labeled images, subset of from Mathis et al. 2018, Nature Neuroscience. The full dataset can be found on [zenodo](https://zenodo.org/record/4008504#.Y2fE7uzMIeY).


You can load those datasets (and create a project) by

1) Clone the DeepLabCut repository:
```git clone https://github.com/DeepLabCut/DeepLabCut```

Check out the GitHub docs, if you need [help](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) for this step.

2) Run the following command:

```
deeplabcut.load_demo_data(config, createtrainingset=False)
```
Where you pass the path to the config file of interest as `config`.


### Big datasets

- [Horse10](http://www.mackenziemathislab.org/horse10) contains >8,000 expertly labeled frames across 30 individual thoroughbred horses.


## Datasets without labels

 - [The Cuttle Shuttle](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/J6XLGK) is a video database of cuttlefish hunting behavior. This dataset contains videos for 6 animals over the course of 16 experimental sessions, each 30 minutes long. *Note: Animal L1-H2013-03 was the most active, and will probably generate the most interesting tracking results. To easily access this animals videos, first change the file view from "Table" to "Tree".*

TODO_TA: any other ideas for datasets?

# Multi Animal Datasets (Day 3)

- [Mont-Blanc bird dataset](https://github.com/DeepLabCut/DeepLabCut_maDLC_DemoData) contains a small dataset of multiple birds.




TODO_AM: link to https://deeplabcut.github.io/DeepLabCut/docs/HelperFunctions.html#model-export-function

TODO_AM: put dataset in standard docs
