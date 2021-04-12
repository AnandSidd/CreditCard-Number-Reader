# CreditCard_Number_Reader
### Steps Involved -
### Step 1:Creating a Credit Card Number Dataset
- Exploring the fonts using digit images and OTSU binarisation.
- Creating the dataset directories.
- Writing augmentation functions.[digitAugmentation,add_noise,pixelate,stretch,preprocess]
- Creating 1000 variations to each digit of the font type sampled.This is train data.
- For Test data we are sampling the same dataset.In actual it is preferred to have real life unseen data from another source.
### Step 2:Training The Model
- Creating Classifier in Keras using LeNet CNN Architecture
- Train the model for 5 epochs.
### Step 3:Extracting A Credit Card from the Background[12 out of 16 digits]
- Using canny edge detection for card boundary.
- Using cv2.findContours() to extract the largest contour.
- Use the function four_point_transform() and order_points() to adjust the perspective of the card.
### Step 4:Use our Model to Identify the Digits.
- First load grayscale extracted image and the original color.
- Apply the Canny Edge algorithm.
- Use findCountours to isolate the digits.
- Sort the contours by size.
- Then sort left to right by creating a function that returns the x-cordinate of a contour.(cv2.moments)
- Find the bounding rectange of the contour which gives us an enclosed rectangle around the digit. 
- Take each extracted digit, use pre_processing function (which applies OTSU Binarization and re-sizes it) then breakdown that image array so that it can be loaded into our classifier.
