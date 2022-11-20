# Using DLC-live

Currently there are four different ways to incorporate _DLC-live!_ into an experimental design:
- **DLC-live SDK** can be used _as is_ in Python, running custom-written scripts to read video data, estimate pose, and interface with the Python APIs for commonly used hardware (Arduino and Teensy microcontrollers, National Instruments devices, Raspberry Pis).
- **DLC-live GUI** provides a graphical user interface to record videos and perform pose estimation without any additional coding. Note that implementation of closed-loop feedback will still require some scripting tailored to the particular application. 
- **Bonsai-DLC** allows easy integration of DLC-based pose estimation into Bonsai experimental control workflows. Find out how Bonsai works in <a href="https://www.frontiersin.org/articles/10.3389/fninf.2015.00007/full" target="_blank">its original technology report</a> and learn about its current capabilities <a href="https://bonsai-rx.org/" target="_blank">on the Bonsai website</a>!
- **Autopilot-DLC** integrates _DLC-live!_ into Autopilot-based control workflows. Check out <a href="https://www.biorxiv.org/content/10.1101/807693v2" target="_blank">the Autopilot whitepaper</a> to learn more about the platform.

```{figure} images/eLife_Kane_etal_Fig1.png
---
height: 350px
name: DLC-live-fig
---
Overview of using DLC networks in real-time experiments within Bonsai, the DLC-Live! GUI, and AutoPilot from <a href="https://elifesciences.org/articles/61909" target="_blank">Kane et al, eLife 2020</a>.
```

```{note}
How can you reach sub-zero latency when providing feedback in a behavior experiment? For what behaviors is this possible, and for which behaviors is it rather impossible?
```

## Getting started

The **FIRST STEP** is to install the _DLC-live!_ pip package.

If you wish to use the **_DLC-live!_ GUI**, follow <a href="https://github.com/DeepLabCut/DeepLabCut-live-GUI/blob/master/docs/install.md" target="_blank">these installation instructions</a>. Note that it requires Python 3.5, 3.6, or 3.7, but do not worry if your CUDA setup is not compatible with TensorFlow (TF) 1.13. You can use <a href="https://www.tensorflow.org/install" target="_blank">Tensorflow 2.x</a> as long as you choose Python 3.7. 

For **other implementations of _DLC-live!_** on Windows or Linux machines, run the following in your DLC environment or create a dedicated environment as described <a href="https://github.com/DeepLabCut/DeepLabCut-live/blob/master/docs/install_desktop.md" target="_blank">here</a>. _DLC-live!_ works with both TF1.x and TF2.x! 
<pre lang="php">pip install deeplabcut-live</pre>

You can test your installation by running `dlc-live-test`. Have a look at the <a href="https://github.com/DeepLabCut/DeepLabCut-live#installation" target="_blank">DLC-live! codebase</a> to see what this test does!

To run _DLC-live!_ on an NVIDIA Jetson Development Board, check out <a href="https://github.com/DeepLabCut/DeepLabCut-live/blob/master/docs/install_jetson.md" target="_blank">this guide</a>. 

The **SECOND STEP** is to export your DLC model of interest or choose a model from the <a href="http://www.mackenziemathislab.org/dlc-modelzoo" target="_blank">DeepLabCut ModelZoo</a>.

To export your own well-trained single-animal model to a <a href="https://developers.google.com/protocol-buffers/" target="_blank">Protocol Buffers (.pb) format</a>, run: 
<pre lang="python">deeplabcut.export_model(cfg_path, iteration=None, shuffle=1, trainingsetindex=0, snapshotindex=None, TFGPUinference=True, overwrite=False, make_tar=True)</pre>

You should now see an `exported-models` folder in your DLC project directory.

Check out the <a href="https://github.com/DeepLabCut/DeepLabCut-live#benchmarkinganalyzing-your-exported-deeplabcut-models" target="_blank"> DLC-live! codebase</a> to see how you can benchmark and analyse your exported DLC models!

## How to use _DLC-live!_ on its own?

To launch and use the _DLC-live!_ GUI, follow the detailed instructions at the <a href="https://github.com/DeepLabCut/DeepLabCut-live-GUI" target="_blank">DeepLabCut-live-GUI codebase</a>.

If you wish to build your own custom software with _DLC-live!_, check out the <a href= "https://github.com/DeepLabCut/DeepLabCut-live#quick-start-instructions-for-use" target="_blank">DLC-live SDK quick-start guide and code</a>!

In either case, <a href="https://github.com/DeepLabCut/DeepLabCut-live/tree/master/dlclive/processor" target="_blank">this guide on the `Processor` class</a> and <a href="https://github.com/DeepLabCut/DeepLabCut-live/tree/master/example_processors" target="_blank">code examples applying it to communicate with Teensy microcontrollers</a> will be especially helpful for building closed-loop experiments. 

## How to use Bonsai-DLC?

If you are new to Bonsai, follow <a href="https://neurogears.org/swc-2020/worksheets/installing/">these instructions</a> to install Bonsai on a Windowso or Linux machine.

Assuming that you already have _DLC-live!_ (and ideally CUDA/TF for GPU support) set up, hook it up with Bonsai by:
1. downloading the `Bonsai.DeepLabCut` and `Bonsai.DeepLabCut.Design` packages from Bonsai _Tools_ -> _Manage packages_; 
2. downloading a suitable (OS- and CPU/GPU-dependent) precompiled TF binary from <a href="https://www.tensorflow.org/install/lang_c" target="_blank">the TF website</a>;
3. copying the `tensorflow.dll` file from the downloaded and extracted TF binary folder to the `Extensions` folder of your Bonsai installation. You can locate your Bonsai install folder by right-clicking on your Bonsai shortcut, selecting _Properties_ and copying the path under "Start in".

For more information on the motivation and installation of Bonsai-DLC, and its source code, visit the <a href="https://github.com/bonsai-rx/deeplabcut" target="_blank">Bonsai-DLC github page</a>. 

As an example, let's see how Bonsai-DLC can be used to control the frequency of a tone based on the Y coordinate of a particular body part.

```{figure} images/bonsaiDLCexample.png
---
height: 98px
name: bonsaiDLCexample
---
An example Bonsai workflow using DLC-live pose estimation to control audio frequency.
```

- insert a **`FileCapture`** source to play a pre-recorded video (for example, the [dog video used by _DLC-live-test_](https://github.com/DeepLabCut/DeepLabCut-live/blob/master/check_install/dog_clip.avi?raw=True) or a recorded experiment) or an appropriate camera source, such as **`CameraCapture`** if you use a webcam, to stream live video. To use other cameras (Basler, FLIR, Vimba), you can find the necessary Bonsai package by browsing _Tools_ -> _Manage packages_ or <a href="https://github.com/orgs/bonsai-rx/repositories" target="_blank">the github repository</a>.
- set the path to your video file or initialise your camera by editing the properties of your source node
- insert a **`PredictPose`** transform node from the DLC package
- set the `ModelFileName` property to the path of your exported `.pb` file and the `PoseConfigFileName` property to the path of your `pose_cfg.yaml`; these could be from the [full_dog model](http://deeplabcut.rowland.harvard.edu/models/DLC_Dog_resnet_50_iteration-0_shuffle-0.tar.gz) of the DLC Model Zoo like in the _DLC-live-test_!
- insert a **`GetBodyPart`** node and set its `Name` property to the label of the body part you wish to use for closed-loop control
- right-click on the **`GetBodyPart`** node and select `Output (Bonsai.DeepLabCut.BodyPart)` -> `Position (OpenCV.Net.Point2f)` -> `Y (float)` -- this will output a stream of Y coordinates of your selected body part
- (optional) insert an **`ExpressionTransform`** node to map the expected range of your coordinates onto a range of sound frequencies; for example, to change the range of values from [200,400] to [100,900], set the `Expression` property of this node to `100+(4*(it-200))`
- insert a **`PropertyMapping`** node followed by a **`FunctionGenerator`** node
- click on the three dots next to the `PropertyMappings` property of the **`PropertyMapping`** node (this will open a PropertyMapping Collection Editor), click _Add_ -> _PropertyMapping_ and select 'Frequency' as property `Name`
- still in the PropertyMapping Collection Editor, click on the three dots next to `Selector` (this will open a Member Selector Editor), click on `Source (float)` and then `>`, which will move the input float (`it`) to the right-side panel
- close the two editors by clicking 'OK'
- (optional) set the `Amplitude` property of **`FunctionGenerator`** to 800 (for example) to increase the sound volume 
- insert an **`AudioPlayback`** sink node to play the sound wave produced by `FunctionGenerator`

Play the workflow by clicking 'Start' in the top panel. You can double-click on any node to visualise what it is doing. Try this for the `PredictPose` and `Position Y` nodes -- the workflow will likely take a few seconds to initialise, so the visualiser windows will be blank at first.

For general Bonsai support, check out the <a href="https://groups.google.com/g/bonsai-users" target="_blank">community google group</a> or <a href="https://github.com/bonsai-rx/bonsai/discussions" target="_blank">github discussions</a>.

## How to use AutoPilot-DLC?
Have a look at the <a href="https://docs.auto-pi-lot.com/en/latest/guide/quickstart.html#realtime-deeplabcut" target="_blank">AutoPilot documentation</a> and an <a href="https://github.com/auto-pi-lot/autopilot/blob/main/examples/transforms/example_transformation_dlc.ipynb" target="_blank">example notebook on the AutoPilot github page</a>.

Return to [readme](../README.md).
