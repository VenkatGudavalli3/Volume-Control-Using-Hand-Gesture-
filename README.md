# Hand Gesture Volume Control

This Python script allows you to control the system volume using hand gestures captured through your computer's webcam. It utilizes OpenCV (`cv2`) for capturing webcam frames, Mediapipe for hand tracking, and pycaw for adjusting the system volume.

## Prerequisites

Before running the script, make sure you have the following libraries installed:

- OpenCV (`cv2`): You can install it using pip with the command:
  ```
  pip install opencv-python
  ```

- Mediapipe: Install it using pip:
  ```
  pip install mediapipe
  ```

- pycaw: To control the system volume, you'll need pycaw. Install it with pip:
  ```
  pip install pycaw
  ```

## Usage

1. Run the script by executing it with Python. It will capture video from your default webcam (`cap = cv2.VideoCapture(0)`).

2. Raise your hand in front of the camera, and the script will detect your hand landmarks and track their movement.

3. Pinch your thumb and index finger together to control the volume. The distance between these two fingers determines the volume level. Move them apart or closer to change the volume.

4. The script will display the volume level and length between your fingers in the terminal.

5. To exit the script, press 'q' in the OpenCV window.

## Adjusting Volume Range

- You can customize the hand gesture range for volume control by modifying the following line:
  ```python
  vol = np.interp(length, [15, 220], [volMin, volMax])
  ```
  Adjust the values `[15, 220]` to set the hand gesture range for volume control. For example, you can increase the 220 value to make the volume gesture require a larger hand movement.

- The volume range is also adjustable:
  ```python
  # Volume range -63.5 (mute) to 0.0 (max volume)
  ```

## Compatibility

This script should work on Windows operating systems as it relies on pycaw for volume control. Ensure that you have an active webcam and the required Python libraries installed.
