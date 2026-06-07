# 🎯 YOLO-SAM Segmentation Pipeline

> An interactive computer vision framework that combines YOLO object detection with Segment Anything Model (SAM) for high-precision instance segmentation on images and videos.

---

# 📖 Overview

The **YOLO-SAM Segmentation Pipeline** is a two-stage AI vision system designed to perform accurate object detection and segmentation with minimal user effort.

The pipeline leverages:

* **YOLO** for fast object localization
* **SAM (Segment Anything Model)** for pixel-level segmentation

By combining the strengths of both models, the system achieves highly accurate object masks while maintaining real-time performance.

The project includes a fully interactive **Google Colab GUI** built using `ipywidgets`, allowing users to upload custom models, process images and videos, visualize segmentation results, and download outputs without writing additional code.

---

# 🚀 Key Features

### 🔍 YOLO Object Detection

Detects objects using state-of-the-art YOLO models.

Supported versions:

* YOLOv8
* YOLOv9
* YOLOv10
* YOLOv11
* Custom-trained YOLO models

---

### 🎭 SAM-Based Segmentation

Uses detected bounding boxes as prompts for SAM.

Benefits:

* Precise object boundaries
* High-quality masks
* Generalized segmentation
* Minimal manual annotation

---

### 📷 Image Segmentation

Process individual images with:

* Detection boxes
* Segmentation masks
* Confidence scores
* Overlay visualization

---

### 🎥 Video Segmentation

Supports frame-by-frame video processing with:

* Object detection
* Mask generation
* Video reconstruction
* MP4 export

---

### 🖥 Interactive User Interface

Built using:

```python
ipywidgets
```

Features:

* Upload models
* Upload images
* Upload videos
* Download results
* Preview outputs

All directly inside Google Colab.

---

### ⚡ GPU Accelerated

Optimized for:

* NVIDIA T4
* A100
* L4
* Local CUDA GPUs

for fast inference.

---

# 🏗 System Architecture

```text
Input Image / Video
          │
          ▼
    YOLO Detection
          │
          ▼
 Bounding Box Prompts
          │
          ▼
      SAM Model
          │
          ▼
 Segmentation Masks
          │
          ▼
 Visualization Layer
          │
          ▼
 Annotated Output
```

---

# ⚙️ Technology Stack

| Component            | Technology                   |
| -------------------- | ---------------------------- |
| Detection            | YOLO                         |
| Segmentation         | Segment Anything Model (SAM) |
| Deep Learning        | PyTorch                      |
| Image Processing     | OpenCV                       |
| Numerical Computing  | NumPy                        |
| UI Framework         | ipywidgets                   |
| Notebook Environment | Google Colab                 |
| Visualization        | Matplotlib                   |

---

# 📦 Installation

## Google Colab Setup

Install required packages:

```bash
!pip install -q ultralytics ipywidgets
```

Enable widget extension:

```bash
!jupyter nbextension enable --py widgetsnbextension
```

---

## Local Installation

Clone repository:

```bash
git clone https://github.com/yourusername/yolo-sam-segmentation.git

cd yolo-sam-segmentation
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Requirements

```text
ultralytics>=8.0.0
opencv-python-headless>=4.8.0
numpy>=1.24.0
ipywidgets>=8.0.0
torch>=2.0.0
torchvision>=0.15.0
```

---

# 🚀 Usage

## Launch Notebook

Open:

```text
yolo_sam_pipeline.ipynb
```

in Google Colab.

---

## Start Interface

Run:

```python
create_ui()
```

This generates the complete graphical interface.

---

## Upload YOLO Model

Supported formats:

```text
.pt
```

Examples:

```text
yolov8n.pt
yolov8s.pt
yolov8m.pt
custom_model.pt
```

---

## Upload SAM Model

Examples:

```text
sam_b.pt
sam_l.pt
sam2_b.pt
custom_sam.pt
```

---

## Process Images

Workflow:

1. Upload image
2. YOLO detects objects
3. SAM generates masks
4. Results displayed automatically

---

## Process Videos

Workflow:

1. Upload video
2. Frame extraction
3. YOLO detection
4. SAM segmentation
5. Video reconstruction
6. Download final output

---

# 📂 Project Structure

```text
YOLO-SAM/
│
├── notebooks/
│   └── yolo_sam_pipeline.ipynb
│
├── models/
│   ├── yolo/
│   └── sam/
│
├── outputs/
│   ├── images/
│   └── videos/
│
├── assets/
│   ├── screenshots/
│   └── examples/
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

# 🔬 Pipeline Workflow

## Step 1 — Object Detection

YOLO detects objects:

```python
results = yolo_model(image)
```

Output:

```text
Class ID
Bounding Box
Confidence Score
```

---

## Step 2 — Bounding Box Prompting

Detected boxes are passed to SAM.

```python
sam.predict(box=box)
```

---

## Step 3 — Segmentation

SAM generates masks:

```python
masks = predictor.predict()
```

Output:

```text
Binary Mask
Confidence Score
Segmentation Area
```

---

## Step 4 — Visualization

Masks are rendered over original media:

```python
overlay_masks(image, masks)
```

Result:

* Colored masks
* Detection labels
* Confidence values

---

# 📊 Example Output

### Input

```text
Image containing:
- Person
- Vehicle
- Building
```

### YOLO Detection

```text
Person → 98%
Vehicle → 96%
Building → 94%
```

### SAM Segmentation

```text
Mask generated for:
✓ Person
✓ Vehicle
✓ Building
```

### Output

```text
Segmented image with pixel-level masks
```

---

# 🎯 Applications

### Military & Defense

* Target detection
* Battlefield object segmentation
* ISR analysis

### Medical Imaging

* Organ segmentation
* Lesion detection
* Radiology workflows

### Autonomous Vehicles

* Road object segmentation
* Pedestrian detection
* Obstacle recognition

### Agriculture

* Crop analysis
* Disease monitoring
* Field mapping

### Smart Cities

* Traffic monitoring
* Crowd analytics
* Infrastructure inspection

### Industrial Automation

* Defect detection
* Quality control
* Asset monitoring

---

# 🔮 Future Improvements

* SAM 2 integration
* Real-time webcam segmentation
* Video object tracking
* Grounding DINO integration
* Multi-modal prompting
* ONNX deployment
* TensorRT acceleration
* Edge AI deployment

---

# 📈 Performance Benefits

| Metric               | Benefit                 |
| -------------------- | ----------------------- |
| Detection Speed      | Fast YOLO inference     |
| Segmentation Quality | Pixel-accurate masks    |
| Scalability          | Supports large videos   |
| Flexibility          | Custom models supported |
| Ease of Use          | No coding required      |

---

# 🤝 Contributing

Contributions are welcome.

1. Fork repository
2. Create feature branch
3. Commit changes
4. Push branch
5. Submit Pull Request

---

# 📜 License

Licensed under the MIT License.

---

# 👨‍💻 Author

**Aravind Pyli**

AI Researcher | Computer Vision Engineer | Machine Learning Enthusiast

### Areas of Interest

* Computer Vision
* Object Detection
* Instance Segmentation
* Medical AI
* Military AI
* Edge AI Systems

---

⭐ If this project helped you, consider giving the repository a star and sharing it with the community.
