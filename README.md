# Speed Challenge

Notebook(s) built to run on Google Colaboratory. Used their GPU runtime to train and run the ML model. <br/>
Used Google Drive to store datasets, checkpoint files, etc. <br/>

## Speed Challenge v1

### Directories (on the Google Drive file system):

comma_challenge<br/>
|<br/>
--- data<br/>
    |<br/>
    --- train and test videos<br/>
    --- training images directory<br/>
    --- test images directory<br/>
    --- checkpoint directory<br/>

### Method

Used OpenCV to calculate optical flow between two frames of the video. For the nth frame, calculated optical flow between the (n-1)th frame and the (n + 1)th frame. Did this for all frames from the 2nd till the penultimate frame. <br/>

Converted optical flow vectors to hsv color values to get BGR image representing the optical flow. <br/>

Used these BGR images to train the model, as well as to make predictions on test data. <br/>

### Model

Built model using Keras<br/>
Series of convolutional layers (with dropout layers in between) followed by dense layers. <br/>
Loss = Mean Squared Error<br/>
Optimizer = Adam<br/>
