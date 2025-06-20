
# 📏 Object Distance Measurement using OpenCV

This project detects two objects (an apple and a pencil) in an image, calculates the distance between them using contour detection and centroids, and visualizes the result using OpenCV and Matplotlib

## 🖼️ Sample Input

> Example image with a red apple and yellow pencil placed apart.

![Sample Input](pen.jpg)

## 🎯 Output Visualization

- Green dots are drawn on the **centers** of the detected objects.
- A **blue line** connects the two centroids.
- Distance between them is calculated using Euclidean distance formula.

![Output Preview](output.jpg) <!-- Replace with actual output image if available -->

## 🛠️ Technologies Used

- Python
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- SciPy (`spatial.distance`)

## 📂 Folder Structure

object-distance-measurement/
├── pen.jpg # Input image with two objects
├── detect_distance.py # Python script
├── output.jpg # Output with drawn centroids and line
├── README.md # Project documentation

## 🧪 Code Overview

```python
contours = sorted(contours, key=cv2.contourArea, reverse=True)[:2]

def get_centroid(c):
    M = cv2.moments(c)
    return (int(M["m10"]/M["m00"]), int(M["m01"]/M["m00"])) if M["m00"] else None

centroids = [get_centroid(c) for c in contours]
cv2.line(img, centroids[0], centroids[1], (255, 0, 0), 2)

distance = euclidean(centroids[0], centroids[1])
print(f"Distance: {distance:.2f}")

▶️ How to Run
Install the required libraries:

copy
pip install opencv-python numpy matplotlib scipy
Place your image as pen.jpg in the project folder.

Run the script:
Copy code

python detect_distance.py
📏 Output Example

Distance between apple and pencil: 182.40
🙋 Author
Madhu Mitha
🎯 GitHub: @madhumithagopinath
