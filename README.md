# Speed Challenge

Notebook(s) built to run on Google Colaboratory. Used their GPU runtime to train and run the ML model. 
Used Google Drive to store datasets, checkpoint files, etc. 

## Speed Challenge v1

### Directories (on the Google Drive file system):

comma_challenge
|
--- data
    |
    --- train and test videos
    --- training images directory
    --- test images directory
    --- checkpoint directory

### Method

Used OpenCV to calculate optical flow between two frames of the video. For the nth frame, calculated optical flow between the (n-1)th frame and the (n + 1)th frame. Did this for all frames from the 2nd till the penultimate frame. 

Converted optical flow vectors to hsv color values to get BGR image representing the optical flow. 

Used these BGR images to train the model, as well as to make predictions on test data. 

### Model

Built model using Keras
Series of convolutional layers (with dropout layers in between) followed by dense layers. 
Loss = Mean Squared Error
Optimizer = Adam
