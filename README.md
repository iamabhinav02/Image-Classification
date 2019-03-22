# Image-Classification

The dataset consists of 13 folders which had 155 images in each. A model using CNN, OpenCV and Keras was used to predict which image belongs in which class.

You can find the dataset here - https://drive.google.com/file/d/1QkAWDrnpLuMs3XfQab9XGNGaJQwEetIq/view for this Assignment.

As it was pretty clear that the dataset had many folders which was named with some label so it was difficult to access those data at a time simultaneously. So first of all I changed the name of all images using a code of os and renamed all the images using the label name followed by index number. For eg. 34_sleeve-0.jpg, 34_sleeve-1.jpg etc.

As the dataset was too large in size so I did some image processing using OpenCV and converted all the images in Black and White with a pixel of 200x200 and stored them in another folder named "input_data_resized". Now this folder contains all the images in the 13 folders i.e. total of 2007 images each of 200x200 pixels in Black and White color.

After converting images into bnw, all the images were converted into an array of pixels and those arrays were stored into a matrix called 'immatrix'.

Then, I manually created all the labels looking into the folder "input_data_resized" and gave them a number 0-12.

Training and Testing data was created by shuffling the input images and using scikit-learn module named train_test_split. All the labels were converted into one-hot encoding format. 

A CNN Model was created then with 2 convolution2D layer 1 maxpooling2D layer, a droput layer which dropped 50% of the data for preventing overfitting. Then it was flattened to give an aaray of data which was then fitted into a neural network with 128 neurons in the first hidden layer and then 13 neurons in the output layer which gave output in one hot encoding format.

This model was created to decide which image would belong to which class and hence an accuracy of 85% was obtained.
