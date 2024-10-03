# Record-Image Acquisition using Web Camera
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
### Developed By: Naveen Kumar B
### Register No:212223230091

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("kabilan.jpg", frame)
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('kabilan',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222100018-kabilan',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222100018-kabilan',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![364794808-8f2bfa2e-2559-4966-bfec-0d8df75a8b3b](https://github.com/user-attachments/assets/49b5d0e1-fc59-457f-a244-834096e417c1)


### ii) Display the video
![364795537-7f17a65c-4eb4-44e7-a07e-f9fb4c9c4a25](https://github.com/user-attachments/assets/0757a311-243e-497b-9cab-4e66babc1975)


### iii) Display the video by resizing the window
![364798032-df0bdb6d-a7e6-4fc6-a0f1-a88584c502ab](https://github.com/user-attachments/assets/3d3bfd76-8d5f-4c1d-bdf7-66b8aaf1eafc)



### iv) Rotate and display the video
![364798083-6f10059f-b84f-4cc3-b346-68b15123ccfd](https://github.com/user-attachments/assets/686c5e29-fee1-4876-884e-a1a960272150)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
