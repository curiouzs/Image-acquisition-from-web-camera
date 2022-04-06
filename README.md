# Image-Acquisition-from-Web-Camera
## AIM
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7


## ALGORITHM 

Step 1:

Use VideoCapture(0) to access web camera

Step 2:

Use imread to read the video or image

Step 3:

Use imwrite to save the image

Step 4:

Use imshow to show the video

Step 5:

End the program and close the output video windows by pressing 'q'.



## Program:


## Developed By: Lokesh Krishnaa M
### Register No: 212220230030

## i) Write the frame as JPG file


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("pic_1.jpg",frame)
cap.release()
cv2.destroyAllWindows()



## ii) Display the video


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window

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
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= smaller_frame
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video

import cv2

import numpy as np

cap=cv2.VideoCapture(0)

while True:

ret,frame=cap.read()

width=int(cap.get(3))

height=int(cap.get(4))

image=np.zeros(frame.shape,np.uint8)

smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)

image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

image[height//2: , :width//2]=smaller_frame

image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

image[height//2:,width//2:]=smaller_frame

cv2.imshow('frame',image)

if cv2.waitKey(1)==ord('q'):

break

cap.release()

cv2.destroyAllWindows()


## Output

### i) Write the frame as JPG image
</br>

![myself jpg - Personal - Microsoft​ Edge 06-04-2022 21_51_05](https://user-images.githubusercontent.com/75234646/162026337-24a8abcd-6513-4a16-8220-f30f316ad6eb.png)


</br>



### ii) Display the video
</br>

![frame 06-04-2022 21_54_06](https://user-images.githubusercontent.com/75234646/162025645-a664d9a5-12b8-4f37-91bc-7b36861a75d1.png)


</br>


### iii) Display the video by resizing the window
</br>


![frame 06-04-2022 21_55_20](https://user-images.githubusercontent.com/75234646/162025667-a72dfd9b-61e7-411f-8bd7-d5a7dcfd7159.png)


</br>




### iv) Rotate and display the video
</br>

![frame 06-04-2022 21_56_09](https://user-images.githubusercontent.com/75234646/162025988-56e0a3a1-7c11-4b32-9f7d-0c9cfb65a80a.png)


</br>



## Result:

Thus the image is accessed from webcamera and displayed using openCV.
