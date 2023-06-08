# FACE-TRACKING
A face tracking program that detects and remembers faces and prints the time for which they were present in a video.


## EXPLANATION:
I have made use of the face_recognition module(version 1.2.3) of python. This module is a great source for pre_trained models for face detection and recognition.
We can basically use two models in this, namely: CNN and HOG

Convolutional neural networks are distinguished from other neural networks by their superior performance with image, speech, or audio signal inputs. They have three main types of layers, which are:

1. Convolutional layer
2. Pooling layer
3. Fully-connected (FC) layer

The convolutional layer is the first layer of a convolutional network. While convolutional layers can be followed by additional convolutional layers or pooling layers, the fully-connected layer is the final layer. With each layer, the CNN increases in its complexity, identifying greater portions of the image. Earlier layers focus on simple features, such as colors and edges. As the image data progresses through the layers of the CNN, it starts to recognize larger elements or shapes of the object until it finally identifies the intended object.

Histogram of Oriented Gradients, also known as HOG, is a feature descriptor like the Canny Edge Detector, SIFT (Scale Invariant and Feature Transform) . It is used in computer vision and image processing for the purpose of object detection. The technique counts occurrences of gradient orientation in the localized portion of an image. This method is quite similar to Edge Orientation Histograms and Scale Invariant aFeature Transformation (SIFT). The HOG descriptor focuses on the structure or the shape of an object. It is better than any edge descriptor as it uses magnitude as well as angle of the gradient to compute the features. For the regions of the image it generates histograms using the magnitude and orientations of the gradient


For this project, I have used CNN as my model, because it provides for slower, but more accurate results.


My project consists of two python files, namely facerec.py and time_per_person_calc.py

### facerec.py

This program takes in a video file and gives an output video file with the detected and recognised faces.

![Screenshot (43)](https://github.com/vaibhavyadav1686/FACE-TRACKING/assets/109307590/df44d58a-1e28-47ed-af13-5bb78f4ef25f)


The program also generates a dictionary, "times", which takes into account the various timestamps for which the particular frame contained a person.
This is helpful in deciding the time for which a person was present in the video.

I have provided a stock video for the program.
I have also provided the output file that I received when I ran the program.



### time_per_person_calc.py

This program calculates the time for which each person was present in the video.
I have attached the output that I got here:
![Screenshot (44)](https://github.com/vaibhavyadav1686/FACE-TRACKING/assets/109307590/6c5d7df6-6b6f-48fb-8702-27d63de23ecd)




It is observed from the above output and from outpy.avi that these IDs may not belong to different persons.
The IDs 1,2 and 3 seem to be taking around 20 seconds each, which is an acceptable result.
The IDs 4,5,6,7 and 8 on the other hand seem to be taking less time. This is not because of the duration for which these people were present in the video, but due to wrong assumption that a new face has been detected.
This is a drawback of these pre-trained models and this can be corrected by checking if a particular ID stays persistent throughout the video or does it glitch in the middle.


Thus, all in all, on testing with the stock video I found out that my program correctly detected and recognized 3 out of 4 persons in the video.
This program has an accuracy of 75% at least.




## STEPS TO WORK WITH THE PROGRAM:
1. Name your input video file "stockvideo.mp4"
2. RUn the facerec.py program
3. Manually select the last generated dictionary containing all the timestamps
4. Paste this into the time_per_person_calc.py program
5. Get your result from the output screen
