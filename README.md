# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

### Developed By:
**Name:** AMIRTHA VARSHINI M

**Register No:** 212224230017

## 💻 Program
```PYTHON
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```
```PYTHON
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
```
```PYTHON
captured_image = cv2.imread('captured_frame.jpg')
```
```PYTHON
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
```PYTHON
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
```PYTHON
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
```PYTHON
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


---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`

<img width="512" height="411" alt="download" src="https://github.com/user-attachments/assets/50bf62d5-4670-42fd-bdc6-c4d62ec2bd00" />


### ii) Display the video
Live webcam video is displayed

<img width="512" height="389" alt="download" src="https://github.com/user-attachments/assets/93d97ffa-7c32-45f4-a112-8b4327587da4" />


### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

<img width="512" height="389" alt="download" src="https://github.com/user-attachments/assets/ca435238-61de-41be-9774-5e93ba56b1ea" />


### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="266" height="389" alt="download" src="https://github.com/user-attachments/assets/1e0805c3-bc4e-4693-9787-f0ee0464829f" />


---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
