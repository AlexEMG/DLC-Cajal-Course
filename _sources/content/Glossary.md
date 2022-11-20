# Glossary

All terms are alphabetically organized.
```{glossary}
[Anaconda](https://www.anaconda.com/products/distribution)
    an open-source distribution of Python (and R) that comes with many useful packages for data science, including {term}`conda`

Anaconda Prompt
    the command line interface for {term}`conda` on Windows machines

annotation
    placement of the specific label(bodypart) on an image

base environment
    the default Python installation that comes with {term}`Anaconda` or {term}`Miniconda` and includes core Python packages; a good rule of thumb is to **never** install new packages into the base environment to avoid corrupting it -- use {term}`virtual environment` instead

batch size
    number of images processed in one iteration of training (max value constrained by GPU memory). More precise term is mini-batch

benchmarking
    the practice of objectively comparing machine learning tools to identify the best-performing ones

bodypart
    also called label, in DeepLabCut is a arbitrarily chosen part of the animal that the user wants to track

[Bonsai](https://bonsai-rx.org/)
    a visual reactive programming language that can be used to generate complex experimental workflows. Its [Bonsai.Deeplabcut package](https://github.com/bonsai-rx/deeplabcut) uses DeepLabCut-live for real-time markerless pose estimation.

[Colab](https://colab.research.google.com/)
    Google Colab is a web based notebook used for writing and executing python code

conda
    an open-source system for managing {term}`packages` and {term}`environments`; comes with {term}`Anaconda` and {term}`Miniconda`

CPU
    central processing unit, also known as the processor, - a key component of any computing device

cropping
    cutting out part of the image, used for reducing computational expense

[CUDA](https://developer.nvidia.com/cuda-zone)
    a parallel computing platform developed by NVIDIA for utilisation of NVIDIA {term}`GPUs`

environment
    see {term}`virtual environment` and {term}`base environment`

dataset
    collection of annotations linked to specific images

detection
    placement of the label by the model

GPU
    graphics processing unit, also known as a "graphics card", capable of high-throughput parallel processing; it greatly accelerates deep learning compared to a {term}`CPU`

ground truth
    coordinates of the label in the immage annotated by the user

identity
    in multianimal DLC a parameter used for specyfing that annotations are subject specific (user can tell the difference between individuals)

IID
    Independent and Identically Distributed, term used for variables that have same probability distribution but are independent from each other (a coin toss always has a 50% chance to be heads or tails, no matter what the previous result of a coin toss was)

inference
    applying a trained model on data i.e. analysis

iteration
    one pass of the batch through the network

jitter
    natural tendency of inferred data to slightly move between frames of analyzed video. Stems from inference happening on image by image basis

MAE
    mean average Euclidean error -- a metric that quantifies the Euclidean distance (what we intuitively understand by the word 'distance') between two observations, such as the manually added and predicted bodypart labels in DLC; proportional to {term}`RMSE`

Markdown
    a lightweight markup language for creating formatted text using a plain-text editor

[Miniconda](https://docs.conda.io/en/latest/miniconda.html)
    a lightweight version of {term}`Anaconda` that includes only {term}`conda` and Python, albeit with fewer pre-installed packages; useful if storage space is of concern, but greater familiarity with the command line might be required

[MoSeq](https://dattalab.github.io/moseq2-website/index.html)
    developed in [Datta's Lab](http://datta.hms.harvard.edu/), an unsupervised machine learning method used to parse mouse behavior

OOD
    Out-of-Domain, a term used to define data that was not used in training the model (a different dataset)

outlier
    a frame in which model made bad detections

package
    a specifically organised collection of Python modules (simply put: Python code) that achieve a common goal; examples include DeepLabCut and TensorFlow

path
    a string of characters that uniquely defines a file or folder location on a computer, e.g. `C:\Users\username\Downloads`

project
    the folder structure and all its contents made during project creation and later work

refinement
    step of the workflow used for correction of bad detections on a subset of outlier frames

RMSE 
    root-mean-square error, measure of difference between values predicted by the model and ground truth

[SimBA](https://github.com/sgoldenlab/simba)
    developed in [Golden's Lab](https://goldenneurolab.com/simba), a framework for training a supervised behavior annotation model

shuffle
    in DeepLabCut: a particular instantiation of train and test sets; multiple shuffles are used for model {term}`benchmarking`

snapshot
    current state of the model with specific weights learned during training

supervised
    a model trained using labeled data with the goal of predicting the labels on unseen data.

terminal
    the command line interface for {term}`conda` on MacOS/Linux machines

training
    process in which the model is learning to find weights that will allow it to solve assigned task (tracking bodyparts)

tracklet
    a fragment of a trajectory, relevant in multi-animal tracking. Tracklets are represented as nodes of a graph, whose edges encode the likelihood that a connected pair of tracklets belongs to the same trajectory

unsupervised
    a model trained without using human annotation, only patterns from the data

[VAME](https://github.com/LINCellularNeuroscience/VAME)
    developed by Kevin Luxem and Pavol Bauer, a framework for unsupervised behavior clustering

virtual environment
    a self-contained Python installation that lets users have different versions of the same Python {term}`packages` on a single machine; great for project management and reproducibility

    when you open the {term}`terminal` (MacOS/Linux) or {term}`Anaconda Prompt` (Windows), the environment you are currently in is displayed in brackets, e.g. `(env) user@MacBook-Pro ~ % ` or `(env) C:\WINDOWS\system32> `

weights
    parameters of a neural network used to process the input (images for DLC)
```
