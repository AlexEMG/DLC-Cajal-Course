# Glossary

All terms are alphabetically organized. 

- annotation - placement of the specific label(bodypart) on an image
- bodypart - also called label, in DeepLabCut is a arbitrarily chosen part of the animal that the user wants to track
- batch size - number of images processed in one iteration of training (max value constrained by GPU memory). More precise term is mini-batch
- Colab - Google Colab is a web based notebook used for writing and executing python code
- cropping - cutting out part of the image, used for reducing computational expense
- dataset - collection of annotations linked to specific images
- detection - placement of the label by the model
- ground truth - coordinates of the label in the immage annotated by the user
- identity - in multianimal DLC a parameter used for specyfing that annotations are subject specific (user can tell the difference between individuals)
- IID - Independent and Indentically Distributed, term used for variables that have same probability diistribution but are independent from eachother (a coin toss alwyas has a 50% chance to be heads or tails, no matter what the previous result of a coin toss was)
- inference - applying a trained model on data i.e. analysis
- iteration - one pass of the batch through the network
- jitter - natural tendency of infered data to slightly move between frames of analyzed video. Stems from inference happening on image by image basis
- MoSeq - developed in [Datta's Lab](http://datta.hms.harvard.edu/), an unsupervised machine learning method used to parse mouse behavior
- OOD - Out-of-Domain, a term used to define data that was not used in training the model (a different dataset)
- outlier - a frame in which model made bad detections
- project - the folder structure and all its contents made during project creation and later work
- refinement - step of the workflow used for correction of bad detections on a subset of outlier frames
- RMSE - root-mean-square error, measure of difference between values predicted by the model and ground truth
- SimBA - developed in [Golden's Lab](https://goldenneurolab.com/simba), a framework for training a supervised behavior annotation model
- snaphsot - current state of the model with specific weights learned during training
- supervised - a model trained using labeled data with the goal of predicting the labels on unseen data. 
- training - process in which the model is learning to find weights that will allow it to solve assigned task (tracking bodyparts)
- unsupervised - a model trained without using human annotation, only patterns from the data
- VAME - developed by Kevin Luxem and Pavol Bauer, a framework for unsupervised behavior clustering
- weights - parameters of a neural network used to process the input (images for DLC)
