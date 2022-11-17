(how-to-install)=
# How To Install DeepLabCut?

Follow <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html" target="_ablank">**the DeepLabCut installation guide**</a>. Ask the teaching assistants for help if you get stuck!

In brief, **if you do not have a GPU on your machine**, all you need to do is:
- install Python - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-1-you-need-to-have-python-installed" target="_blank">Step 1 in the DLC installation guide</a> describes the easiest way to do this;
- install DeepLabCut - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-2-please-use-our-supplied-conda-environment" target="_blank">Step 2 in the DLC installation guide</a> explains what to do depending on your operating system.

For the steps that require a GPU, you will use DeepLabCut on Google Colab.

**If you have an Apple M1/M2 GPU**, follow the two steps above, but make sure to install Python with miniconda3. If you have anaconda instead, have a look at <a href="https://deeplabcut.github.io/DeepLabCut/docs/recipes/installTips.html#deeplabcut-macos-m1-and-m2-chip-installation-environment-instructions" target="_blank">this MacOS-specific guidance</a>!

**If you have an NVIDIA GPU** and wish to engage it, your order of business will be slightly more involved. What you do depends on whether your machine has other versions of CUDA/TensorFlow installed - see <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#system-wide-considerations" target="_blank">this note on system-wide installation</a>.

If you have Ubuntu, it is recommended that you use <a href="https://hub.docker.com/r/deeplabcut/deeplabcut" target="_blank">Docker</a>. You can follow these detailed instructions <a href="https://deeplabcut.github.io/DeepLabCut/docs/recipes/installTips.html#installation-on-ubuntu-18-04-lts" target="_blank">for Ubuntu 18.04</a> or <a href="https://deeplabcut.github.io/DeepLabCut/docs/recipes/installTips.html#installation-on-ubuntu-20-04-lts" target="_blank">Ubuntu 20.04</a> and also have a look at <a href="https://deeplabcut.github.io/DeepLabCut/docs/docker.html" target="_blank">these notes on DLC Docker containers</a>!

If you use Windows OS and **do not** have other versions of CUDA installed:
- install Python - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-1-you-need-to-have-python-installed" target="_blank">Step 1 in the DLC installation guide</a> describes the easiest way to do this;
- install an NVIDIA driver:
    - check what GPU your machine has;
    - install an appropriate driver for your GPU/OS from the <a href="https://www.nvidia.com/download/index.aspx" target="_blank">NVIDIA website</a>
    - you can check which driver is installed by typing `nvidia-smi` in the terminal
    - check that your NVIDIA driver <a href="https://docs.nvidia.com/deploy/cuda-compatibility/index.html#minor-version-compatibility" target="_blank">will work with CUDA 11.x</a>!
- set up CUDA - <a href="https://medium.com/analytics-vidhya/installing-cuda-and-cudnn-on-windows-d44b8e9876b5" target="_blank">this medium article</a> details the steps involved
    - the most recent version of TensforFlow (TF-2.10 which will get installed along with DeepLabCut) <a href="" target="_blank">works with CUDA-11.2</a>
    - get your Visual Studio 2019 (free) Community version <a href="https://my.visualstudio.com/Downloads?q=visual%20studio%202019&wt.mc_id=o~msft~vscom~older-downloads" target="_blank">here</a>
    - get CUDA-11.2 (or another version if needed) <a href="https://developer.nvidia.com/cuda-toolkit-archive" target="_blank">here</a>
    - get cuDNN-8.1 (or another version if needed) <a href="https://developer.nvidia.com/rdp/cudnn-archive" target="_blank">here</a> - you will need to create an NVIDIA developer profile 
    - type `nvcc -V` in the terminal to check that it prints the correct CUDA runtime version
- install DeepLabCut - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-2-please-use-our-supplied-conda-environment" target="_blank">Step 2 in the DLC installation guide</a> explains what you should do;
- verify that your GPU is recognised by running `python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"` (it is not? double-check that you followed all steps in the medium article linked above!)

If you use Windows OS and **do** have other versions of CUDA installed:
- install Python - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-1-you-need-to-have-python-installed" target="_blank">Step 1 in the DLC installation guide</a> describes the easiest way to do this;
- install DeepLabCut - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-2-please-use-our-supplied-conda-environment" target="_blank">Step 2 in the DLC installation guide</a> explains what you should do;
- add the TF2.10-compatible CUDA toolkit to your new DLC conda environment by running `conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0`
- verify that your GPU is recognised by running `python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"`

Something gone awry? Check out these <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#troubleshooting" target="_blank">troubleshooting tips</a> and reach out to teaching assistants!

Return to [readme](../README.md).
