# Ex. No: 02 Record Image Acquisition using Web Camera
## NAME: ALAGESHWARI V
## Reg No: 212224240010

## AIM:
To acquire an image using a web camera and display the video with resizing and rotation using Python and OpenCV.

## PROCEDURE:
1. Import the required libraries, such as OpenCV and Matplotlib.
2. Initialize the web camera using cv2.VideoCapture(0).
3. Capture an image and save it as a file.
4. Read and display the captured image using Matplotlib.
5. Capture and display video frames from the web camera.
6. Resize the video frames to the required dimensions using cv2.resize().
7. Rotate the video frames by 90° clockwise using cv2.rotate().
8. Release the camera after completing the operations.

## CODE:
```python
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

## OUTPUT:

<img width="617" height="500" alt="image" src="https://github.com/user-attachments/assets/3c1f18ad-34e5-4669-ab79-daa08d63a014" />
<img width="612" height="457" alt="image" src="https://github.com/user-attachments/assets/8532f7d5-1707-472e-b905-a22bfc083071" />
<img width="307" height="461" alt="image" src="https://github.com/user-attachments/assets/a641521e-55d7-4cc8-bbcd-547d6b54dfc4" />
<img width="345" height="462" alt="image" src="https://github.com/user-attachments/assets/d539fce8-7078-4e30-a974-0e36369809e9" />

## RESULT:

Thus the Image Acquisition using Web Camera was verified succeccfully.

