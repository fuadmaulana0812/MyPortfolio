# Face Expression Recognition

### Objective
Objective of the project is to detect facial expressions. Expressions detect such as angry, disgust, neutral, happy, surprise, fear, and sad. This system can be very helpful to detection of customer satisfaction based on facial expressions that appear.

### Dataset
I use [Facial Expression Recognition](https://docs.google.com/uc?export=download&confirm=t&id=1b4DZIS7VfBI_V8-DbpsaCP0ij8u1K3hJ) dataset where the data is in the form of facial images that have been done with a grayscale process. The dataset used has been divided into 2 folders, namely train and validation. 

<img align="center" width="500" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/bedfa25030933028af3d89d8334a1c1f2be1fe66/Projects/Face%20Expression%20Recognition/Images/face_image.png">

The dataset consist of train and validation with a total 28821 images of train data and 7066 images of validation data. With the distribution of labels or expressions in the data train as follows

<img align="center" width="500" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/cacc822785d55fef83e2e3ce0a870b9c15d4f816/Projects/Face%20Expression%20Recognition/Images/labels_distribution.png">

I divided validation data to validation and test with a ratio of 6:4.

### Data Augmentation
I did the data augmentation process to increase the data with several possibilities such as tilting the image, flipping the image horizontally, shifting the position of the image, and zooming in on the image. The purpose of this process is to reproduce the data so that the model created will be more accurate.

### Build and Evaluate Model
The model that I created is a tensorflow model with the following model architecture

<img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/9.png"> <img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/6.png"><img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/3.png">
<img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/8.png"> <img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/5.png"> <img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/2.png">
<img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/7.png"> <img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/4.png"><img align="center" width="300" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/dcde4797f57c6ef77e17ca6a2f26143259f79a46/Projects/Face%20Expression%20Recognition/Images/Model/1.png">

The model stops at epoch 41 because it uses earlystopping to avoid overfitting. The model obtained has an accuracy of 0.68 in training and 0.66 in validation.

<img align="center" width="900" height="50" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/f55dff12184bbdab86b8c725fe5d512fb4839f23/Projects/Face%20Expression%20Recognition/Images/acc_model.png">

The following is a graph of the accuracy and loss of the model for each epoch.

<img align="center" width="400" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/ac82d36706d03588cb751e8ef396ae89634e7820/Projects/Face%20Expression%20Recognition/Images/acc_graph.png"> <img align="center" width="400" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/ac82d36706d03588cb751e8ef396ae89634e7820/Projects/Face%20Expression%20Recognition/Images/loss_graph.png">

### Test Prediction
From a total of 1416 images in the test data, the accuracy obtained is 64%. 

<img align="center" width="700" height="80" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/16ce79994da442fa2af4a74023c16539e1b904c7/Projects/Face%20Expression%20Recognition/Images/acc_test.png">

The following is the distribution of the predicted results for each class

<img align="center" width="500" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/16ce79994da442fa2af4a74023c16539e1b904c7/Projects/Face%20Expression%20Recognition/Images/cr.png">

It can be seen that the model is better at predicting class happy, while disgust is not good. This is influenced by the amount of data in each class. The more data, the better the model in predicting. Here is how the model predicts facial images

<img align="center" width="900" height="500" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/16ce79994da442fa2af4a74023c16539e1b904c7/Projects/Face%20Expression%20Recognition/Images/pred_test.png">
