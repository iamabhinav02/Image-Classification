# Image-Classification

The dataset consists of 13 folders which had 155 images in each. A model using CNN, OpenCV and Keras was used to predict which image belongs in which class.

You can find the dataset here - https://drive.google.com/file/d/1QkAWDrnpLuMs3XfQab9XGNGaJQwEetIq/view for this Assignment.

As it was pretty clear that the dataset had many folders which was named with some label so it was difficult to access those data at a time simultaneously. So first of all I changed the name of all images using a code of os and renamed all the images using the label name followed by index number. For eg. 34_sleeve-0.jpg, 34_sleeve-1.jpg etc.

As the dataset was too large in size so I did some image processing using OpenCV and converted all the images in Black and White with a pixel of 200x200 and stored them in another folder named "input_data_resized". Now this folder contains all the images in the 13 folders i.e. total of 2007 images each of 200x200 pixels in Black and White color.

After converting images into bnw, all the images were converted into an array of pixels and those arrays were stored into a matrix called 'immatrix'.

Then, I manually created all the labels looking into the folder "input_data_resized" and gave them a number 0-12.

Training and Testing data was created by shuffling the input images and using scikit-learn module named train_test_split. All the labels were converted into one-hot encoding format. 

A CNN Model was created which looked like this: 
      ________________________________________________________________
Layer (type)                  Output Shape                  Param #   
=================================================================
conv2d_1 (Conv2D)             (None, 32, 198, 198)                 320       
_________________________________________________________________
conv2d_2 (Conv2D)             (None, 30, 196, 32)                 57056     
_________________________________________________________________
max_pooling2d_1(MaxPooling2   (None, 15, 98, 32)                  0         
_________________________________________________________________
dropout_1 (Dropout)           (None, 15, 98, 32)                  0         
_________________________________________________________________
flatten_1 (Flatten)                 (None, 47040)                 0         
_________________________________________________________________
dense_1 (Dense)                     (None, 128)                   6021248   
_________________________________________________________________
dropout_2 (Dropout)                 (None, 128)                   0         
_________________________________________________________________
dense_2 (Dense)                     (None, 13)                    1677      
=================================================================

Total params: 6,080,301
Trainable params: 6,080,301
Non-trainable params: 0

This model was created to decide which image would belong to which class and hence an accuracy of 85% was obtained.
