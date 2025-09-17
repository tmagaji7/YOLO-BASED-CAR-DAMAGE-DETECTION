# YOLO-Based Car Damage Detection 🚗🔧

This repository contains an implementation of **YOLOv8** for car damage detection.  
The model has been trained on the **CarDD dataset** (Car Damage Detection dataset) and is capable of identifying different types of vehicle damages from images.

---

## 📂 Repository Structure

```
Car-Damage-Detection/
│── YOLO_Based_Car_Damage.ipynb   # Training & inference notebook
│── args.yaml                     # Training configuration file
│── weights/
│    └── last.pt                  # Trained YOLOv8n model weights
│── README.md                     # Project documentation
```

---

## ⚙️ Setup Instructions

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/YOLO-BASED-CAR-DAMAGE-DETECTION.git
   cd YOLO-BASED-CAR-DAMAGE-DETECTION
   ```

2. Install dependencies:
   ```bash
   pip install ultralytics opencv-python matplotlib
   ```

3. Verify YOLO installation:
   ```bash
   yolo help
   ```

---

## 🏋️ Training

The model was trained using YOLOv8 with the following command:

```bash
yolo detect train data=CarDD.yaml model=yolov8n.pt epochs=50 imgsz=640
```

- **Model:** YOLOv8n (nano version for fast inference)  
- **Dataset:** CarDD (custom annotated dataset)  
- **Results:** mAP50 ~ 90% (example, update with your exact result)  

---

## 🔎 Inference

Run inference on test images:

```bash
yolo detect predict model=weights/last.pt source="path/to/test/images"
```

Or use the notebook (`YOLO_Based_Car_Damage.ipynb`) for interactive testing.

---

## 📦 Export Model

For deployment, export the model to different formats:

```bash
yolo export model=weights/last.pt format=onnx
yolo export model=weights/last.pt format=torchscript
```

---

## 🚀 Deployment

- **Raspberry Pi / Edge devices** → Use `torchscript` or `onnx` export for lightweight inference.  
- **Web / Mobile apps** → Convert to ONNX → TensorRT / CoreML.  
- **Cloud APIs** → Serve using FastAPI/Flask + ONNXRuntime.

---

## 📊 Results Visualization

- Training curves, confusion matrix, and precision-recall plots are available in the notebook.  
- Example detections:  
  ![Sample Detection](https://user-images.githubusercontent.com/00000000/sample.png)

---

## 👨‍💻 Author

- **Tarun M. Magaji**  
- GitHub: [tmagaji7](https://github.com/tmagaji7)  

---

## 📜 License

This project is released under the MIT License.
