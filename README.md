# ASL-Translator
Project Description: Have you ever met someone who was deaf and you wanted to have a conversation with them? Well look no further. With this American Sign Language Translator, you will be able to hold a simple conversation with them. This program will be able to classify and display the  American Sign Language on the screen from A-Z. 

**DEMO:**
https://streamable.com/r5tql

**Documentation:**	
	** PLEASE NOTE THAT THIS IS FOR WINDOWS 10 ** 
	
**Tools:**
Anaconda
Tensorflow-GPU 1.13
CUDA
cuDNN
Faster-RCNN-Inception-V2
Pillow
Lxml
Cython
Contextlib2
Jupyter
Matplotlib
Pandas
OpenCV-python

**How to Run:**
After downloading the repo and all the required tools, cd into the object detection folder and run the cmd line “idle”. 
Click on file > open > object_detection_webcam.py
It will open a new window. Hit run > run module.
Start holding up American Sign Language
You might need a GPU (I had a Nvidia GTX 1060)


**Installation Instructions:**	
Install Anaconda, CUDA, and cuDNN
Install necessary tools in requirments.txt
Install Tensorflow-gpu v1.13
Downgrade GPU graphics drivers to 4.17 (For Nvidia GTX 1060 at least)
Run this commmand: “set PYTHONPATH=C:\tensorflow2\models;C:\tensorflow2\models\research;C:\tensorflow2\models\research\slim”
If you have a GPU you can run the script. If you don’t you might have to retrain using the SSD-MobileNet Model.
**Please note that you might need to move the asl tensorflow2 folder out into your C drive. If you don’t you'll need to edit multiple lines of code and change some commands**

**Challenges and Solutions:**
The checkpoints wouldn’t save while training, and would hang. The GPU would drop to 0% utilization and it took an average of 2 seconds per step.
To solve this, I had to downgrade my GPU graphics drivers all the way back to version 417. It seems like the current graphics drivers automatically had an incompatible CUDA version (10.3 I believe?) so we had to go back to a version with a compatible CUDA version (which is 10.1 and 10.0).
Getting similar training data with different lighting and backgrounds. Labeling the images was also a challenge. 
It took a very long time to get different training data with different background and lightings and different hands. In total we had close to 1300~ training images and 120~ testing images. Labeling it was a sensitive job because we all had to box and label it similarly to avoid conflicts. Not only that, but it took each of us about 2-3 hours to finish labeling our data sets.
There was a mislabeled image.
A problem was that someone mislabeled an image which resulted in errors and the record files not being created correctly. I had to go back and edit the xml file and csv files.
The webcam script would only detect from A-F.
We were able to solve this by changing one line of code in the script that would only detect up to 6 classes. We changed it accordingly to 26.

**References:**
[Youtube Tutorial](https://github.com/EdjeElectronics/TensorFlow-Object-Detection-API-Tutorial-Train-Multiple-Objects-Windows-10)
[Tensorflow Issues Board](https://github.com/tensorflow/models/issues)

