#The execution code was modified to implement in the Colab environment

### Build instructions
##### 1. No need to compile it, builders are in /SAMBuilder and /TclBuilder.

##### 2. Install Tensorflow if you haven't. 

```
%tensorflow_version 2.x
import tensorflow as tf
print(tf.__version__)
```
###### Colab environment has tensorflow version 2.0 or higher installed.

####
```
%cd /content

!git clone git@github.com:LiniXiang/BIM2SAM.AI.git
```
####

### Training the neural net
```
%cd /content/BIM2SAM.AI/Python/NeuralNets
!python BIM2FeaturesNN_V1.py
```
### Use the neural net in a BIM->SAM->tcl pipeline. This will generate a tcl file that can be run in OpenSees:
```
%cd /content/BIM2SAM.AI/Python
!sudo chmod 744 /content/BIM2SAM.AI/Cpp/SAMBuilder/SAMBuilder
!sudo chmod 744 /content/BIM2SAM.AI/Cpp/TclBuilder/TclBuilder
!python main.py
```

### How to cite
Charles Wang, Caigui Jiang, Stella X. Yu, Frank McKenna, & Kincho H. Law. (2019, October 18). NHERI-SimCenter/BIM2SAM.AI: Release v1.0 (Version 1.0). Zenodo. http://doi.org/10.5281/zenodo.3509957


