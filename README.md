# Image_Acqusition-_using_Web_Camera

## Aim : 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
<br>i) Write the frame as JPG 
<br>ii) Display the video 
<br>iii) Display the video by resizing the window
<br>iv) Rotate and display the video

## Software Used :
Anaconda - Python 3.7

## Algorithm :
### Step 1 :
Open the webcam using cv2.VideoCapture(0) and capture frames.
### Step 2 :
Capture frames repeatedly inside a loop.
### Step 3 :
Rotate each captured frame 90° clockwise using cv2.rotate().
### Step 4 :
Convert the rotated frame from BGR to RGB for display.
### Step 5 :
Show the rotated video frames with matplotlib, refreshing after each frame.

## Program :
``` 
Developed By: NITHYA D
Register No: 212223240110
```
### i) Write the frame as JPG file :
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
### ii) Display the video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
### iii) Display the video by resizing the window
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
### iv) Rotate and display the video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## Output :
### i) Write the frame as JPG image :
<img width="638" height="504" alt="image" src="https://github.com/user-attachments/assets/8dea2cef-667e-4bbd-ad62-ed7026c7cd19" />

### ii) Display the video
<img width="623" height="468" alt="image" src="https://github.com/user-attachments/assets/4aae3c9a-5a98-4239-8ea9-82bff5c2d64c" />

### iii) Display the video by resizing the window
<img width="313" height="473" alt="image" src="https://github.com/user-attachments/assets/a1189439-5ff1-4caf-bafb-94172a79bb4a" />

### iv) Rotate and display the video
<img width="353" height="469" alt="image" src="https://github.com/user-attachments/assets/96ead6d0-2cb4-4689-b16a-be8f36e95104" />

## Result :
Thus the image is accessed from webcamera and displayed using openCV.
