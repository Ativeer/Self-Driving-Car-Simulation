## Self Driving Car Simulation
### A project on Reinforcement Learning to simulate a self driving car

### Asbtract:
Trained a convolutional neural network (CNN) to map raw pixels from a single front-facing camera directly to steering commands. This end-to-end approach proved surprisingly powerful. With minimum training data from humans the system learns to drive in traffic on local roads with or without lane markings and on highways. It also operates in areas with unclear visual guidance such as in parking lots and on unpaved roads.
The system automatically learns internal representations of the necessary processing steps such as detecting useful road features with only the human steering angle as the training signal. I never explicitly trained it to detect, for example, the outline of roads.


### Introduction:

In this project, we describe a CNN that goes beyond pattern recognition. It learns the entire processing pipeline needed to steer an automobile. The roundwork for this project was done over 10 years ago in a Defense Advanced Research Projects Agency (DARPA) seedling project known as DARPA Autonomous Vehicle (DAVE) in which a sub-scale radio control (RC) car drove through a junk-filled alley way. DAVE was trained on hours of human driving in similar, but not identical environments.

Nine months ago, a new effort was started at NVIDIA that sought to build on DAVE and create a robust system for driving on public roads. The primary motivation for this work is to avoid the need to recognize specific human-designated features, such as lane markings, guard rails, or other cars, and to avoid having to create a collection of “if, then, else” rules, based on observation of these features. This project tries to implement the efforts of NVIDIA to verify its results.

### Network Architecture:

We train the weights of our network to minimize the mean squared error between the steering command output by the network and the command of either the human driver, or the adjusted steering command for off-center and rotated images. The network architecture is shown in training script. The network consists of 9 layers, including a normalization layer, 5 convolutional layers and 3 fully connected layers. The input image is split into YUV planes and passed to the network. The first layer of the network performs image normalization. The normalizer is hard-coded and is not adjusted in the learning process. Performing normalization in the network allows the normalization scheme to be altered with the network architecture and to be accelerated via GPU processing.
The convolutional layers were designed to perform feature extraction and were chosen empirically through a series of experiments that varied layer configurations. The strided convolutions is used in the first three convolutional layers with a 2×2 stride and a 5×5 kernel and a non-strided convolution with a 3×3 kernel size in the last two convolutional layers. Followed by the five convolutional layers are three fully connected layers leading to an output control value which is the inverse turning radius. The fully connected layers are designed to function as a controller for steering in the NVIDIA paper.

### Steps to run the code

- I am attaching my code, dataset link and model weights and checkpoint for you to test it out yourself. Also, attaching a video to determine how the output looks like for the simulation.


- Link to dataset: https://drive.google.com/drive/folders/1Y10Ket-t07pP8zuVF5rjs9wQSfWGWO6d?usp=sharing

- Place the code within the working directory.
- Download the dataset from above provided link and unzip it in your working directory, or link it to your google colab the way I did (just change the path to the dataset).

- Run the code for it to train.

- Once trained, you will have model logs and the model itself within the google drive folder (make sure the path is changed to your needs)

- Download them and run the second file, model_atan.ipynb file to see the model in action.

- Place the steering_wheel_image.jpg in the Dataset folder that you downloaded on your local machine and the models folder within the working directory.
- FYI, you need the dataset in your local machine if you are testing the model in your machine.
- Make sure to fix the path according to your system.

- DrivingTestVideo provides a sample video output of my Project.

### HyperParameters:

- The Hyperparameters were selected based on the values provided by the NVIDIA paper found here : https://arxiv.org/pdf/1604.07316.pdf%5D
- The people working at NVIDIA tested with variety of models and found this to work the best for the DQN model.
- This practice could take days to just train for one particular set of hyperparameters, thus it is better to use just the set of input to check if it is valid for a DQN as well.
- Result of the model can be found in the _model_atan_ notebook.