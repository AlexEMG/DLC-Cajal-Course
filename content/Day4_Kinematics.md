# Kinematics Analysis

Motion capture is widely used in biomechanics and motor neuroscience.

## DLC2Kinematics

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

For more details and options, please refer to <a href="https://github.com/AdaptiveMotorControlLab/DLC2Kinematics/blob/master/DEMO.ipynb" target="_blank">DLC2Kinematics demo notebook</a>.

Another option is using <a href="https://github.com/JojoReikun/ClimbingLizardDLCAnalysis" target="_blank">DOKA</a>, which Johanna Schultz mentioned and created together with Fabian Plum and others.

[Let’s go back 🔙](Day4_Practicals.md).
