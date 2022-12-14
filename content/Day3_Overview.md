# Overview Day 3

Welcome to day 3✨!

We will start our day with a number of [lectures](Day3_Lectures.md) covering topics from multi-animal pose estimation, via real-time experiments to the model zoo 😎. 

In the [practical part](Day3_Practicals.md), we will keep improving our DeepLabCut models from yesterday. If you're in tracking multiple animals, go to [practical part for multiple animals](Day3_maPracticals.md).

Then you can also work with the [Model Zoo and DLC-live](Day3_ModelZoo.md) (try to reserve at least 1h for this).

## Day 3: Take home messages

```{Tip}
- What is active learning?
- How do you get a good pose tracking model?
```

## Day 3: Major goals ⚽️

```{important}
- Let's try to have some videos well analyzed (i.e. good pose estimation prediction). Then we will be able to dig into kinematics or supervised and unsupervised behavioral analysis!
```

How can you check if the videos are well analyzed 🤔?
- Create labeled videos 📽 and watch them to see if the predictions on new videos are accurate. You can use: `deeplabcut.create_labeled_video`.
- visualize the trajectories over time, and check if the trajectories are smooth, which is normally the case for biological motion, unless, e.g., your frame rate is very small. You can use: `deeplabcut.plot_trajectories`, check out the figure below to get an idea of what is the output.

For both features, refer to [the user guide 📕](https://github.com/DeepLabCut/DeepLabCut/blob/master/docs/standardDeepLabCut_UserGuide.md#k-plot-trajectories) for details.

<p align="center">
<img src="https://images.squarespace-cdn.com/content/v1/57f6d51c9f74566f55ecf271/1559946148685-WHDO5IG9MMCHU0T7RC62/ke17ZwdGBToddI8pDm48kEOb1vFO6oRDmR8SXh4iL21Zw-zPPgdn4jUwVcJE1ZvWEtT5uBSRWt4vQZAgTJucoTqqXjS3CfNDSuuf31e0tVG1gXK66ltnjKh4U2immgm7AVAdfOWODmXNLQLqbLRZ2DqWIIaSPh2v08GbKqpiV54/file0289.png?format=500w" height="240">
<img src="https://images.squarespace-cdn.com/content/v1/57f6d51c9f74566f55ecf271/1559939762886-CCB0R107I2HXAHZLHECP/ke17ZwdGBToddI8pDm48kNeA8e5AnyMqj80u4_mB0hV7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z5QPOohDIaIeljMHgDF5CVlOqpeNLcJ80NK65_fV7S1UcpboONgOQYHLzaUWEI1Ir9fXt7Ehyn7DSgU3GCReAA-ZDqXZYzu2fuaodM4POSZ4w/plot_poses-01.png?format=1000w" height="250">
</p>


[Let’s go back 🔙](../README.md).
