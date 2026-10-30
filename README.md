# Image Capture and Video Processing Using OpenCV
### Developed By:
## Name: POOJA SRI P
## Register No: 212224230197  

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
```.PY
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

# Capture image
cap = cv2.VideoCapture(0)
ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()

# Read captured image
captured_image = cv2.imread('captured_frame.jpg')

# Display captured image
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()

# Display live webcam video
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

# Resize video frame
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

# Rotate video frame
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

## Output

### i) Write the frame as JPG image
<img width="652" height="522" alt="image" src="https://github.com/user-attachments/assets/bd482bf7-48c4-4f37-9410-844ef206b224" />


### ii) Display the video
<img width="652" height="496" alt="image" src="https://github.com/user-attachments/assets/1a85b3fc-23f5-4d9c-bb3a-352449bc525a" />

### iii) Display the video by resizing the window
<img width="357" height="498" alt="image" src="https://github.com/user-attachments/assets/dff9647a-349b-416d-b515-6b09561e3e49" />


### iv) Rotate and display the video
<img width="387" height="490" alt="image" src="https://github.com/user-attachments/assets/5445d7cc-4a31-49b6-b042-8d36181466a8" />


---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
