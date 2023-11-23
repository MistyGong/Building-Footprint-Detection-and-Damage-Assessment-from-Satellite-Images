# Building-Footprint-Detection-and-Damage-Assessment-from-Satellite-Images

**1. the code is basically doing 3 things:**
   a. read the 6 images and conduct image-processing on them (i.e. sharpening the images, increasing brightness and contrast)
   b. train a customized yolov5 model using 3 images I found satellite images online that contains building, airplanes, cars and trucks. This is because the pre-trained yolov5 model doesn't have high accuracy on the images. 
   I used labelImg to label these 3 images and save the output as YOLO format. Then direct the path in the dataset.yml file in the yolov5 folder to where the training images & labels were stored. The next step is training the model with the data
   However, the customized yolov5 model does perform better but it is still doesn't have a super high accuracy and this is due to a lack of training data and computer memories.
   c. the last section is to generate the json file that contains all the detection of the building and save it as a JSON file
**2. for the rest of the task I wasn't able to complete. But I would approach it with the method below:**
   a. printing out images with the detection label on it
   b. could use labelling tools like labelImg, makesenseAI or labelme etc to label buildings that are considered damaged. Run the yolo model to train on this and use the trained model to make detection on images that we want to be tagged. 
   c. depending on the definition of damaged building, we can use a set of training images, and give each image a label ranging from 'none' to 'low,' 'medium,' 'high,' or 'full' using the criteria we had, encode the labels and then run a CNN model on these training dataset. The next step is testing with different hyperparameters such as filter, kernal_size, stride, activation and loss function as well as optimizer etc. Once we get good performance based on the classification_report, we can start using the model to assess the degree of building damage.
