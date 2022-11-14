# Day 4 Practicals

## Using Moseq with pose tracking data

Motion Sequencing (MoSeq): a method to discover the syllables and grammar that comprise mouse 🐁 behavior. Recently Caleb Weinreb and colleagues have been expanding this approach, which originally relied on depth sensing technology, to work with pose estimation data. Thus, it is broadly applicable, independent of what cameras were used in experiments.

<img src="https://dattalab.github.io/moseq2-website/images/crowd_movie_example.gif?format=2500w" width="550" title="maDLC" alt="maDLC" align="center" vspace = "0">

Figure showing example behavioral syllables, [Source: Datta Lab, Harvard Medical School](https://dattalab.github.io/moseq2-website/index.html).

A detailed overview over Moseq 2 can be found on <a href="https://dattalab.github.io/moseq2-website/index.html" target="_blank">the project's website.</a>

Colab: https://colab.research.google.com/drive/14UGWm6RolWkhJxB3wx0ozYlzgDwJlDBW?usp=sharing

Data: https://drive.google.com/drive/folders/1UNHQ_XCQEKLPPSjGspRopWBj6-YNDV6G?usp=share_link

Repo: https://github.com/calebweinreb/keypointMoSeq/tree/user_friendly_pipeline

TODO_AM: will be refactored

## Kinematics analysis based on pose tracking data

Motion capture is widely used in biomechanics and motor neuroscience.

### DLC2Kinematics

One way to perform kinematics analysis based on DeepLabCut outputs, is using <a href="https://github.com/AdaptiveMotorControlLab/DLC2Kinematics" target="_blank">DLC2Kinematics</a>.

It has a simple interface and you can visualize as well as manipulate pose estimation data. Here is a simple code example:

``` python
# Importing the library:
import dlc2kinematics
# Load data data (from your predictions)
df, bodyparts, scorer = dlc2kinematics.load_data(<path of the h5 file>)
# Computing velocities:
df_vel = dlc2kinematics.compute_velocity(df,bodyparts=['all'])
# Compute acceleration for some body parts:
df_vel = dlc2kinematics.compute_acceleration(df,bodyparts=['nose','joystick'])
```

For more details and options, please refer to <a href="https://github.com/AdaptiveMotorControlLab/DLC2Kinematics" target="_blank">DLC2Kinematics</a>.

### DOKA

https://github.com/JojoReikun/ClimbingLizardDLCAnalysis

### What else?



## Discussion topics



TODO_TA: What else?


[Let’s go back 🔙](../README.md).
