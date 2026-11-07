# 🎓 Cheating Tracking and Alert System

## 📌 Project Overview
An AI-powered classroom monitoring system designed to detect and track student behaviors during examinations using Computer Vision and Deep Learning.

The system analyzes exam videos, identifies classroom behaviors, tracks detected objects, and highlights potentially suspicious activities for human review.

**Important:** The system provides behavioral indicators only. It does not determine or prove that cheating has occurred.

## 🎯 Project Objectives
- Detect student behaviors in examination environments.
- Identify potentially suspicious activities such as phone usage and head turning.
- Track detected objects across video frames.
- Generate visual alerts to support human supervision.
- Provide an interactive interface for video analysis.

## 🧠 Technologies Used
- Python
- YOLOv8 (Object Detection)
- ByteTrack (Object Tracking)
- OpenCV
- Streamlit
- Pandas

## 📂 Dataset
The project uses the **Classroom Behavior** dataset from Roboflow Universe.

[Dataset Source – Roboflow Universe](https://universe.roboflow.com/paris-75/classroom-behavior-ziw3p)

The dataset contains 1,329 images divided into:
- Training: 1,008 images
- Validation: 216 images
- Testing: 105 images

### Behavior Classes
1. eating_drinking
2. focusing
3. lookup
4. raising_hand
5. sleeping
6. study
7. turning_head
8. unknown
9. using_pc
10. using_phone

## ⚙️ Model Training
A pretrained YOLOv8n model was fine-tuned on the classroom behavior dataset.

Training configuration:
- Image Size: 640 × 640
- Batch Size: 16
- Epochs: 30
- Optimizer: Ultralytics default configuration
- Tracking Algorithm: ByteTrack

## 📊 Model Evaluation

| Metric | Test Result |
|---|---:|
| Precision | 80.0% |
| Recall | 80.4% |
| mAP@50 | 85.1% |
| mAP@50-95 | 64.4% |

Performance varies across behavior classes. In particular, `turning_head` requires further improvement.

## 🖥️ Application Features
- Upload examination videos.
- Analyze videos using YOLOv8.
- Track detected behaviors using ByteTrack.
- Display annotated video frames.
- Highlight potentially suspicious behaviors for review.

## 🚀 Installation and Usage

### 1. Clone the repository
```bash
git clone YOUR_REPOSITORY_URL
cd Cheating-Tracking-and-Alert-System
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the application
```bash
python -m streamlit run app.py
```

### 4. Model File
Place the trained `best.pt` file in the project root directory, alongside `app.py`.

## 🔮 Future Improvements
- Improve `turning_head` detection.
- Add automated evidence screenshots.
- Develop an incident history dashboard.
- Improve tracking consistency.
- Add real-time monitoring capabilities.

## ⚠️ Limitations and Ethical Considerations
- Model predictions may contain false positives and false negatives.
- Looking away or using a phone does not independently prove cheating.
- All alerts must be reviewed by a human supervisor.
- Video data should be collected and processed with appropriate authorization and privacy safeguards.

## 👨‍💻 Author
**Tarek Sabry**

Data Science & AI Enthusiast

---

⭐ If you find this project useful, feel free to explore and contribute.
