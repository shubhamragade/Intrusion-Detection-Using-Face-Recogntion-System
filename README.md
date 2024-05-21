# FaceDetectionApplication Integrated Python, DL, WhatsApp service and Email service , haarcascade for face recognition, and LBPH for model training

face_classifier.detectMultiScale accepts 6 arguments , but works with single argument also. 
passing array of pic information is must, but here we are passing scale factor (always > 1) and min neighbours value also.
we have used scale factor = 1.4, so that, it will reduce the size of detected face upto 40% to get detected by the algorithm.
While training we fix the size of image. This means that this size of face is detected in the image if present.
However, by rescaling the input image, you can resize a larger face to a smaller one, making it detectable by the algorithm.
With scale factor, we increase the chance of a matching size with the model for detection is found. This also means that 
the algorithm works slower if we will user lower value of scale factor, since it will be more thorough.
We can increase it to as much as 1.4 for faster detection, with the risk of missing some faces altogether.
we have used minNeighbour = 6, because we have only one face, so theres no chance to loose any faces, wven with heighr value.
if we will use min neighbour = 0 ,then it will search for unlimited number of faces, and will return so many false positives, 
so to get more accuracy, means if we want our algo to capture only real true positives, then we should go for higher value of min neighbour, 
heigher value of min neighbour means higher accuracy, but with this chancs of loosing true positives or increase in false negative
also increases, so we have to try various value to get the exact one, but normaly 2-6 works fine. 


putText function of cv2 module is used to put the text (should be in string format), on the image.
it requires 6 arguments,(image, string, position where string needed to show, font type, size of txt, colour of text, width of text)
                    
    Availble font lists
    FONT_HERSHEY_COMPLEX
    FONT_HERSHEY_COMPLEX_SMALL
    FONT_HERSHEY_DUPLEX
    FONT_HERSHEY_PLAIN
    FONT_HERSHEY_SCRIPT_COMPLEX
    FONT_HERSHEY_SCRIPT_SIMPLEX
    FONT_HERSHEY_SIMPLEX
    FONT_HERSHEY_TRIPLEX
    FONT_ITALIC
    
    
    Initialize facial recognizer
model = cv2.face.createLBPHFaceRecognizer()
NOTE: For OpenCV 3.0 use cv2.face.createLBPHFaceRecognizer()
pip install opencv-contrib-python
model = cv2.createLBPHFaceRecognizer()

#os.path.isfile() method in Python is used to check whether the specified path is an existing regular file or not.
#os.path.join for concatenating various path components with exactly one directory separator (‘/’)
#listdir() method in python is used to get the list of all files and directories in the specified directory
