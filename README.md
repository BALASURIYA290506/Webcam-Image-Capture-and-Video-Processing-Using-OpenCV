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

## 💻 Program

### Developed By:
Name: M BALASURIYA

### Register No: 212224240021

---

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
```python
import cv2

cap = cv2.VideoCapture(0)
if not cap.isOpened():
    raise RuntimeError("Cannot open webcam")

ret, frame = cap.read()          # capture a single frame
if ret:
    cv2.imwrite("captured_image.jpg", frame)
    print("Captured image is saved as captured_image.jpg")
else:
    print("Failed to capture frame")

cap.release()
```
### ii) Display the video
Live webcam video is displayed
```python
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break
    cv2.imshow("Live Video", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```python
import cv2

cap = cv2.VideoCapture(0)

cv2.namedWindow("Resized Video", cv2.WINDOW_NORMAL)   # allows the window to be resized
cv2.resizeWindow("Resized Video", 640, 480)

while True:
    ret, frame = cap.read()
    if not ret:
        break
    cv2.imshow("Resized Video", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```python
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break

    frame = cv2.resize(frame, (640, 480))                 # resize to 640 x 480
    rotated = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)  # rotate 90° clockwise

    cv2.imshow("Rotated Video (90° Clockwise)", rotated)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`

<img width="640" height="480" alt="captured_image" src="https://github.com/user-attachments/assets/2b44c2e7-47bc-4a8a-8ec6-568d56eaa763" />


### ii) Display the video
Live webcam video is displayed

<img width="636" height="507" alt="image" src="https://github.com/user-attachments/assets/20daa2ad-e58b-4760-977f-04717d9154bb" />


### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

<img width="635" height="511" alt="image" src="https://github.com/user-attachments/assets/9301084a-8c2c-4061-b005-c23b5659edbf" />


### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="478" height="670" alt="image" src="https://github.com/user-attachments/assets/2fb3a419-4cb9-4e03-b39d-8332dbc257d9" />




## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
