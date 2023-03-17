# Image-Acquisition-from-Web-Camera
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
<br>
Import cv2 and capture the video using cv2.VideoCapture(0)
### Step 2:
<br>
Write the captured image using cv2.imwrite("pic.jpg",frame)
### Step 3:
<br>
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
### Step 4:
<br>
Display the image until the loop gets over.
### Step 5:
<br>
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).
## Program:
``` Python
### Developed By:Sangeetha.K
### Register No:212221230085

## i) Write the frame as JPG file
```
import cv2
cam = cv2.VideoCapture(0)
while(True):
    ret,frame = cam.read()
    cv2.imwrite("pic.jpg",frame)
    result = False
cam.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('x'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:,:width//2]=smaller_frame
    image[:height//2,width//2:]=smaller_frame
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1)==ord('x'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import numpy as np
import cv2
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('x'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
</br>
![Screenshot 2023-03-17 210953](https://user-images.githubusercontent.com/93992063/225954742-8f74dcbd-5250-452b-921a-f58dc47d47a9.png)
</br>
### ii) Display the video
</br>
![Screenshot 2023-03-17 200749](https://user-images.githubusercontent.com/93992063/225954779-ef765673-2b10-4e5e-9a25-58c4237a443a.png)
</br>
### iii) Display the video by resizing the window
</br>
![Screenshot 2023-03-17 201044](https://user-images.githubusercontent.com/93992063/225954808-b90b433f-a4ff-4360-8bc9-c84150076215.png)
</br>

### iv) Rotate and display the video
</br>
![Screenshot 2023-03-17 201205](https://user-images.githubusercontent.com/93992063/225954847-e2ea42ce-c3f3-488c-8d3a-6b08ab5b8e20.png)
</br>


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
