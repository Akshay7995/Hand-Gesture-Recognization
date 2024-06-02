# Hand-Gesture-Recognization

This project implements a basic hand gesture recognition system using OpenCV and Python. It detects the number of fingers extended in a user's hand within a designated region of interest (ROI).

Functionality:

(i)Video Capture: Opens the default webcam (index 0) using OpenCV's VideoCapture class.

(ii)Frame Processing:

*Captures a frame from the webcam.

*Flips the frame horizontally for natural viewing (cv2.flip).

*Defines a kernel for image processing operations (np.ones).

(iii)Region of Interest (ROI):

*Defines a rectangular ROI in the center of the frame for hand detection (cv2.rectangle).

*Extracts the ROI for further processing.

(iv)Skin Color Detection:

*Converts the ROI to HSV color space (cv2.cvtColor).

*Defines a range for skin color in HSV (lower_skin, upper_skin).

*Uses color segmentation to create a mask that isolates the hand (cv2.inRange).

(v)Hand Enhancement:

*Applies morphological operations to fill in dark spots within the hand (cv2.dilate).

*Smooths the mask to reduce noise (cv2.GaussianBlur).

(vi)Contour Detection:

*Finds contours in the mask, representing the hand's outline (cv2.findContours).

*Chooses the contour with the largest area (assuming it corresponds to the hand).

(vii)Finger Counting:

*Iterates through defects:

**Calculates the triangle formed by a defect, its start and end points.

**Applies the cosine rule to estimate the angle between defect and fingertip.

**Filters out irrelevant defects based on angle and distance thresholds.

**Increments the finger count for each valid defect.

(vii)Gesture Display:

*Overlays the number of detected fingers (l) on the original frame (cv2.putText).

*Handles edge cases like no hand detected or too many fingers.

(vii)Window Display:

*Shows the original frame (frame) and the mask (mask) for visualization.

*Waits for user input (cv2.waitKey).
