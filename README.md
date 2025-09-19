Object-Tracking-and-Counting-using-YOLOv8
This project is an advanced object detection and tracking system that uses the YOLOv8 deep learning model to accurately identify, track, and count multiple classes of objects in a video stream.
It is designed to be highly versatile, working on various video types, from drone footage to security camera recordings. The system provides a real-time count of all unique objects it detects and tracks throughout the video.
The project is built on the Ultralytics YOLOv8 framework, for real-time object detection. It is powered by the YOLOv8x model, which was chosen after a performance analysis showed it provides the optimal balance between detection accuracy and computational efficiency for this application.

Features:
Real-time Object Detection: Utilizes the YOLOv8 model for high-performance object detection.
Multi-Class Detection: Capable of detecting multiple object classes from the COCO dataset, including people, cars, bicycles, birds, and more.
Robust Object Tracking: Employs a simple yet effective tracking algorithm to assign a unique ID to each detected object, ensuring accurate counting across frames.
Dynamic Video Processing: The script is designed to accept any video file as a command-line argument, making it highly flexible.
Performance-Optimized: Processes a subset of frames to balance real-time performance with detection accuracy.

Usage
To run the object detection script, simply execute the main.py file from your terminal, providing the path to your video file as an argument.
python main.py path/to/your/video.mp4

Technical Details
Model: The project uses the pre-trained YOLOv8m model. This model was selected as it provides the optimal balance between high detection accuracy and computational efficiency for this application.

Libraries:
ultralytics: Core library for using the YOLOv8 model.
OpenCV (cv2): Used for video processing, including reading frames and displaying the output.
cvzone: Provides simplified functions for drawing bounding boxes and text.
pandas: Used for efficiently handling model detection data.
Tracking Algorithm: The project uses a simple centroid-based tracking algorithm. It calculates the center point of each detected object's bounding box and matches it to the center points of objects from previous frames. If a new detection is within a certain distance threshold of an existing object, it is considered the same object and is assigned the same ID.

Future Improvements
The project can be significantly enhanced by training a custom YOLOv8 model on a specialized dataset. This is particularly useful for niche applications where the pre-trained model may not perform optimally.

Why Custom Training?
Improved Accuracy: The pre-trained YOLOv8 models are great for general-purpose detection, but they may struggle with objects that are very small, at unusual angles (like from a drone), or in unique lighting conditions. A custom model, trained on your specific data, will be highly optimized for these scenarios.

Expanded Class Support: You can train the model to detect and classify new object types that are not included in the original COCO dataset.
To get started with custom training, you would need to:
Gather a diverse dataset of images or video frames.
Annotate the objects in your dataset with a labeling tool (e.g., LabelImg, Roboflow).

Train a new YOLOv8 model using the Ultralytics framework, which is well-documented for this purpose.
