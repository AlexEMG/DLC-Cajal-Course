# How-To Install DeepLabCut:

DeepLabCut can be run 🏃‍♂️ on Windows, Linux, or macOS.

Follow <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html" target="_ablank">**the DeepLabCut installation guide**</a>. 
You can always ask the teaching assistants 📢 for help if you get stuck✨!

In brief, **if you do not have a GPU on your machine**, all you need to do is:
- install Python - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-1-you-need-to-have-python-installed" target="_blank">Step 1 in the DLC installation guide</a> describes the easiest way to do this;
- install DeepLabCut - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-2-please-use-our-supplied-conda-environment" target="_blank">Step 2 in the DLC installation guide</a> explains what to do depending on your operating system.

For the steps that require a GPU, you can use DeepLabCut on <a href="https://colab.research.google.com/" target="_blank">Google Colab</a> 😉!

**If you have an Apple M1/M2 GPU**, have a look at <a href="https://github.com/DeepLabCut/DeepLabCut/blob/master/docs/installation.md#install-anaconda-or-use-miniconda3-ideal-for-macos-users" target="_blank">this MacOS-specific guidance</a>! This new, easy installation works for MacOS versions 12.5.1 and higher so check your version first and update if necessary.


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
    - the most recent version of TensforFlow (TF-2.10 which will get installed along with DeepLabCut) <a href="https://www.tensorflow.org/install/source_windows#gpu" target="_blank">works with CUDA-11.2</a>
    - get your Visual Studio 2017 (free) Community version <a href="https://download.visualstudio.microsoft.com/download/pr/4035d2dd-2d45-48eb-9104-d4dc7d808a7b/f5675416a31cbf8c29e74d75a1790cf7/vs_community.exe" target="_blank">here</a>
    - get CUDA-11.2 (or another version if needed) <a href="https://developer.nvidia.com/cuda-toolkit-archive" target="_blank">here</a>
    - get cuDNN-8.1 (or another version if needed) <a href="https://developer.nvidia.com/rdp/cudnn-archive" target="_blank">here</a> - you will need to create an NVIDIA developer profile 
    - type `nvcc -V` in the terminal to check that it prints the correct CUDA runtime version
- if you want to automatically install all the packages used in this course you can use a batch script (Windows only!) provided here: <a href="https://drive.google.com/file/d/1TilfFvGgqRkqFDwli4YnHECGRkEQ3_Mi/view?usp=sharing" target="_blank">.
  Simply run it as administrator. It will create a `Repositories` directory on your `C` drive and download all necessary repositories and install everything for you. If you do it, skip the steps below.
- install DeepLabCut - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-2-please-use-our-supplied-conda-environment" target="_blank">Step 2 in the DLC installation guide</a> explains what you should do;
- verify that your GPU is recognised by running `python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"` (it is not? double-check that you followed all steps in the medium article linked above!)

If you use Windows OS and **do** have other versions of CUDA installed:
- install Python - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-1-you-need-to-have-python-installed" target="_blank">Step 1 in the DLC installation guide</a> describes the easiest way to do this;
- install DeepLabCut - <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#step-2-please-use-our-supplied-conda-environment" target="_blank">Step 2 in the DLC installation guide</a> explains what you should do;
- add the TF2.10-compatible CUDA toolkit to your new DLC conda environment by running `conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0`
- verify that your GPU is recognised by running `python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"`

Something gone awry? Check out these <a href="https://deeplabcut.github.io/DeepLabCut/docs/installation.html#troubleshooting" target="_blank">troubleshooting tips</a> and reach out to teaching assistants!

[Let's go  back 🔙](../README.md).

