# xray-check
This repo contains a model that is generated to classify whether the input image is xray image or not on Tensorflow.

## Data
There are two classes used; first class contains xray images with 846 images and second class contains random images with 846 images.

- Dataset is divided into training (90%) and test (10%) sets. 

- For xray images in the dataset, open datasets for Chest Radiography XRAY images are used:
  - https://github.com/ieee8023/covid-chestxray-dataset
  - https://www.kaggle.com/c/rsna-pneumonia-detection-challenge

- For random image dataset "https://picsum.photos" is used to generate random images.

## Model

- Keras library is used to generate the classifier and CNN architecture is used for the classifier. 
- In the input layer, 32 convolutional filters with size 3x3 added with relu activation function. Inputs are accepted as 200x200 with RGB colors which makes input shape 200x200x3.
- Max pooling added with 3x3 filter after convolution.
- After max pooling, 2 hidden layers added to model. 
- First hidden layer consists of 32 convolutional filters with size 3x3 with relu activation function and then maxpooling with 2x2 filter added.
- Second hidden layer consists of 64 convolutional filters with size 3x3 with relu activation function and then maxpooling with 2x2 filter added.
- Then, flatten operation is applied.
- Fully connected layer is added with 64 units with relu activation function.
- Later, dropout technique is applied with the rate of 0.5 to avoid overfitting.
- Finally, fully connected layer is used with 1 unit with sigmoid function (1, if the image is xray iamge; 0, otherwise).

For the compilation of the classifier, SGD optimizer is used for optimizer and binary_crossentropy is used as loss function.
