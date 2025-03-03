# YOLOv3 Object Detection in Google Colab

A straightforward project demonstrating how to run real-time (single-frame) object detection using [YOLOv3](https://pjreddie.com/darknet/yolo/) in [Google Colab](https://colab.research.google.com/). This repo includes a notebook that allows you to capture a photo from your local webcam via a JavaScript interface, then detects objects (including people) on that image, drawing bounding boxes and labels.

---

## Features

- **Colab Webcam Capture**  
  Uses JavaScript within the Colab environment to snap an image from your local camera (browser-based).
  
- **YOLOv3 Inference**  
  Supports real-time object detection for 80+ classes (COCO dataset).

- **Bounding Boxes & Labels**  
  Displays detected objects with bounding boxes, confidence scores, and class labels.

- **Easy Setup**  
  Automatically downloads YOLOv3 config (`yolov3.cfg`), weights (`yolov3.weights`), and class names (`coco.names`) directly within the notebook.

---

## Getting Started

1. **Clone or Download the Repository**  
   ```bash
   git clone https://github.com/dumpsterdj/yolo-colab-webcam.git
   cd yolo-colab-webcam
   ```

2. **Open the Notebook in Colab**  
   - Open [Google Colab](https://colab.research.google.com/).
   - Upload or open the `colab_yolo_detection.ipynb` notebook.  

3. **Install & Load YOLO**  
   - Run the first cell to install necessary dependencies (OpenCV, NumPy) and to automatically fetch `yolov3.cfg`, `yolov3.weights`, and `coco.names`.

4. **Capture an Image**  
   - The notebook provides a “Capture” button (from the JavaScript cell) that taps into your local webcam.  
   - Click **Capture** to snap a photo—this will save a file `photo.jpg` within the Colab file system.

5. **Detection**  
   - The code loads your captured image, passes it through the YOLO network, and draws bounding boxes with labels and confidence scores.  
   - The result is displayed inline with `cv2_imshow`.

---

## File Overview

- **`colab_yolo_detection.ipynb`**  
  A Colab notebook with all the steps:
  1. Download YOLO files (config, weights, names).  
  2. Install dependencies (OpenCV, NumPy).  
  3. Use a JavaScript snippet to capture an image from your local webcam.  
  4. Run object detection and visualize results.

- **`LICENSE`**  
  Details the terms under which this project is licensed (MIT by default).

- **`README.md`**  
  This file, providing an overview of the project.

---

## Requirements

- **Google Colab environment**  
  (no need to install Python locally if you run everything in Colab)
- **Camera**  
  Access via your browser to capture images.
- **Python 3.7+**  
  (Already included in Google Colab)
- **OpenCV**  
  Installed via `!pip install opencv-python` in the Colab notebook.

---

## Usage Tips

- **Confidence Threshold**  
  Adjust `CONF_THRESH` in the notebook (default is `0.5`) if you want more or fewer detections.
- **Non-Max Suppression (NMS)**  
  Tweak `NMS_THRESH` (default is `0.3`) if you see multiple overlapping boxes for the same object.
- **Custom Logic**  
  For example, if `label == "person"`, you could trigger a custom action (logging, alert, etc.).

---

## Acknowledgments

- [PJ Reddie’s Darknet](https://pjreddie.com/darknet/) – for developing YOLOv3.  
- [OpenCV documentation](https://docs.opencv.org/) – for the DNN module.  
- [Google Colab Community](https://research.google.com/colaboratory/) – for tips on leveraging the camera in notebooks.

---

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use, distribute, and modify it. 
