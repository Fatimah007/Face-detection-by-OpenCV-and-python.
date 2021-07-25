# Face-detection-by-OpenCV-and-python.


In ubento i installed opencv and python.

1/Install openCv and python
$sudo apt install python-pip
$ pip install opencv-python

2/download the trained classifier XML file (haarcascade_frontalface_default.xml)
data/haarcascades/haarcascade_frontalface_default.xml
Save in  my working location.

3/
perform the face detection for each frame in a video. Here is the code:

import cv2

# Load the cascade
face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')

# To capture video from webcam. 
cap = cv2.VideoCapture(0)
# To use a video file as input 
# cap = cv2.VideoCapture('filename.mp4')

while True:
    # Read the frame
    _, img = cap.read()
    # Convert to grayscale
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    # Detect the faces
    faces = face_cascade.detectMultiScale(gray, 1.1, 4)
    # Draw the rectangle around each face
    for (x, y, w, h) in faces:
        cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
    # Display
    cv2.imshow('img', img)
    # Stop if escape key is pressed
    k = cv2.waitKey(30) & 0xff
    if k==27:
        break
# Release the VideoCapture object
cap.release()

4/ in the terminal of Ubuntu write the Following to run the camera.
4.1/ cd /home/fatimah/Downloads/python
python is the folder where i saved the python code(detect_face).

4.2/Write the python then the name of the pyton code(detect_face)
fatimah@fatimah-VirtualBox:~/Downloads/python$ python detect_face.py

I used Ubuntu so the camera didn’t show up. 
