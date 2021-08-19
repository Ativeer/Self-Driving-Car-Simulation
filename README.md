## Self Driving Car Simulation
### A project on Reinforcement Learning to simulate a self driving car

### Asbtract:
Trained a convolutional neural network (CNN) to map raw pixels from a single front-facing camera directly to steering commands. This end-to-end approach proved surprisingly powerful. With minimum training data from humans the system learns to drive in traffic on local roads with or without lane markings and on highways. It also operates in areas with unclear visual guidance such as in parking lots and on unpaved roads.
The system automatically learns internal representations of the necessary processing steps such as detecting useful road features with only the human steering angle as the training signal. I never explicitly trained it to detect, for example, the outline of roads.


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