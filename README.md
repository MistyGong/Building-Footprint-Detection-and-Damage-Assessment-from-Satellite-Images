# Building-Footprint-Detection-and-Damage-Assessment-from-Satellite-Images

**1. the code achieves 3 things:**
   - Reads the 6 images and conducts image processing on them (i.e. image sharpening, optimising contrast and brightness)
   - Trains a customized yolov5 model using 3 satellite images from an online source which contains buildings, aeroplanes, cars and trucks. This is because the pre-trained yolov5 model doesn't have a high accuracy on the object identification as a baseline. I used labelImg to label these 3 images and save the output in YOLO format. Then direct the path in the dataset.yml file in the yolov5 folder to where the training images & labels are stored. The next step is training the model with the data. Despite the trained yolov5 model performing substantially better than the baseline, it still has plenty of room for accuracy improvements due to a lack of training data and computer memory.
   - the last task is to generate the JSON file and save all the building detection data using the trained yolov5 model.


   
**2. for the rest of the task I wasn't able to complete. But I would approach it with the method below:**
   - printing out images with the detection labels attached
   - could use labelling tools like labelImg, makesenseAI or labelme etc to label buildings that are considered damaged. Run the yolo model to train on this and use the trained model to make detection on images that we want to be tagged.
   - depending on the definition of a damaged building, we can use a set of training images, and give each image a label ranging from 'none' to 'low,' 'medium,' 'high,' or 'full' using the criteria we had, encode the labels and then run a CNN model on this training dataset. The next step is testing with different hyperparameters such as filter, kernal_size, stride, activation and loss function as well as optimizer etc. Once we get good performance based on the classification_report, we can start using the model to assess the degree of building damage.
