Live Object Detection with YOLOv8 and Streamlit
Real-time webcam object detection application using YOLOv8 and Streamlit web interface.

Features
Real-time Detection: Live webcam feed with object detection
YOLOv8 Model: Uses Ultralytics YOLOv8n (nano) for fast detection
Class Filtering: Detects specific home objects
Confidence Threshold: Filters detections above 40% confidence
Streamlit UI: Clean web interface with wide layout
Supported Objects
Class ID

Object

2

Person

20

Backpack

40

Cup

42

Spoon

43

Mirror

48

Scissors

67

Cellphone

Requirements

Copy code
Python 3.8+
streamlit
opencv-python
ultralytics
numpy
Installation
Clone the repository
bash


git clone https://github.com/yourusername/your-repo.git
cd your-repo
Create virtual environment (recommended)
bash 

python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
Install dependencies
bash 

pip install -r requirements.txt
Usage
Run the Streamlit application:

bash


streamlit run app.py
The application will open in your default browser at http://localhost:8501.

Project Structure


├── app.py              # Main Streamlit application
├── requirements.txt   # Python dependencies
├── README.md          # This file
└── yolov8n.pt         # YOLOv8 model (downloaded automatically)
How It Works
Model Loading: YOLOv8n model is cached using @st.cache_resource
Webcam Capture: OpenCV captures video from camera (index 0)
Detection: Each frame is analyzed for defined object classes
Visualization: Bounding boxes are drawn on detected objects
Display: Processed frames shown in Streamlit interface
Configuration


Camera Index: Change cv2.VideoCapture(0) for different camera
Resolution: Adjust CAP_PROP_FRAME_WIDTH/HEIGHT
Confidence: Modify threshold if conf > 0.4
Classes: Update HOME_CLASSES list for different objects
Troubleshooting
Camera not opening
Ensure no other application is using the camera
Check camera permissions
Try different camera index: cv2.VideoCapture(1)
Model download failing
Check internet connection
Manually download from Ultralytics GitHub
Performance issues
Close other applications using webcam
Reduce frame resolution
Use GPU if available
License
MIT License

Acknowledgments
Ultralytics for YOLOv8
Streamlit for the web framework
OpenCV for computer vision tools


