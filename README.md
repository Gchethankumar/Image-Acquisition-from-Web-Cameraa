# Image-Acquisition-from-Web-Cameraa
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the viedo using cv2.ViedoCapture(0). 

### Step 2:
Write the capture image using cv2.imwrite("NewPicture.jpg",frame).

### Step 3:
Resize the image using cv2.resize(frame,(0,0),fx=0.5,fy=0.5).

### Step 4:
Display the image until the loop gets over.

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180).

## Program:
```
Developed By:G.Chethan Kumar
Register No:212222240022
```
## i) Write the frame as JPG file
``` Python
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
``` Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('212222240022-GChethankumar',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
``` Python
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
    cv2.imshow('212222240022_Gchethankumar',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
``` Python
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
    cv2.imshow('212222240022_Gchethankumar',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![NewPicture](https://github.com/Gchethankumar/Image-Acquisition-from-Web-Cameraa/assets/118348224/23301cc5-a7f5-41ba-8373-2e09c49454a0)


### ii) Display the video

![Screenshot from 2023-08-22 17-53-51](https://github.com/Gchethankumar/Image-Acquisition-from-Web-Cameraa/assets/118348224/714ce1ee-504c-43dd-a1b4-068120dd98c4)


### iii) Display the video by resizing the window

![Screenshot from 2023-08-22 18-22-06](https://github.com/Gchethankumar/Image-Acquisition-from-Web-Cameraa/assets/118348224/c1cd5d22-a4e3-469c-a391-cabd30de1d36)


### iv) Rotate and display the video

![Screenshot from 2023-08-22 18-27-11](https://github.com/Gchethankumar/Image-Acquisition-from-Web-Cameraa/assets/118348224/145f94a8-a9dd-4a5c-aa74-324d1709a50d)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
