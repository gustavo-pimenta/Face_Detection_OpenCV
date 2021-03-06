# Video_Detection_OpenCV
 Python script to detect and classify faces using OpenCV and the Cascade System.

## Skin Color Filter
In this project i used skin color, to reconize a hand in the region of interest, usings image processing techniques to get the Contour of the hand.
The image is filtered in HSV color system, then the image noise are removed with size threshold, Gaussian Blur, erosion and dilation to get a clear contour.
With the contour's angles, is possible to find convexity defects in areas between each finger, descovering how many fingers are beeing showed in the video.


## Cascade Classifier

### Main Function - cascade.detectMultiScale(image, scaleFactor, minNeighbors)
#### scaleFactor – Parameter specifying how much the image size is reduced at each image scale.
    Basically the scale factor is used to create your scale pyramid. More explanation can be found here. In short, as described here, your model has a fixed size defined during training, which is visible in the xml. This means that this size of face is detected in the image if present. However, by rescaling the input image, you can resize a larger face to a smaller one, making it detectable by the algorithm.
    1.05 is a good possible value for this, which means you use a small step for resizing, i.e. reduce size by 5%, you increase the chance of a matching size with the model for detection is found. This also means that the algorithm works slower since it is more thorough. You may increase it to as much as 1.4 for faster detection, with the risk of missing some faces altogether.
#### minNeighbors – Parameter specifying how many neighbors each candidate rectangle should have to retain it.
    This parameter will affect the quality of the detected faces. Higher value results in less detections but with higher quality. 3~6 is a good value for it.
