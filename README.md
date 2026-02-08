# 🛰️ SAM2 Object Tracking

## 📌 Project Overview
This project implements a multi-object tracking pipeline using **Meta’s Segment Anything Model 2 (SAM2)** to track objects across image frames.  
It demonstrates segmentation-driven tracking, bounding box extraction, and performance evaluation using IoU metrics on the CMU10_3D dataset.

SAM2 is a promptable visual segmentation foundation model designed for images and videos, capable of generating masks and tracking objects across frames using points, boxes, or masks as prompts. :contentReference[oaicite:0]{index=0}  
It extends the original SAM by incorporating transformer-based streaming memory for real-time video processing and strong generalization across visual tasks. :contentReference[oaicite:1]{index=1}  

---

## 🎯 Objective
- Track 10 object categories across multiple viewpoints
- Use SAM2 segmentation for object tracking
- Convert masks into bounding boxes
- Evaluate performance using Intersection over Union (IoU)
- Produce visual and statistical analysis

---

## 🗂️ Dataset
- **Dataset:** CMU10_3D  
- **Images Processed:** 258  
- **Object Categories**
  - can_chowder
  - can_soymilk
  - can_tomatosoup
  - carton_oj
  - carton_soymilk
  - diet_coke
  - hc_potroastsoup
  - juicebox
  - rice_tuscan
  - ricepilaf

---

## ⚙️ Methodology

### 1️⃣ Environment Setup
- Installed SAM2 model with PyTorch & CUDA
- Configured notebook environment

### 2️⃣ Initialization
- Extracted initial bounding boxes from ground truth masks

### 3️⃣ Tracking Pipeline
- Used SAM2 video predictor
- Generated segmentation masks
- Converted masks → bounding boxes
- Propagated tracking across frames

### 4️⃣ Evaluation
- Compared predictions vs ground truth
- Calculated IoU scores
- Generated performance breakdown

---

## 📊 Results Summary

| Metric | Value |
|--------|------|
| Images Processed | 258 |
| Mean IoU | **0.4417 (44.17%)** |
| Best Object | carton_oj (54.19%) |
| Worst Object | ricepilaf (23.94%) |

### Prediction Quality
- Excellent (IoU ≥ 0.7): 33.3%
- Good (0.5–0.7): 10.0%
- Acceptable (0.3–0.5): 17.0%
- Poor (<0.3): 39.8%

---

## 📦 Repository Contents
```
SAM2-Object-Tracking/
│
├── SAM2_Object_Tracking.ipynb
├── sam2_predictions.csv
├── ground_truth_boxes.csv
├── iou_results.csv
├── README.md
```

---

## 🚀 Installation

### Clone Repository
```bash
git clone https://github.com/HrushikeshBoddu/SAM2-Object-Tracking.git
cd SAM2-Object-Tracking
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

### Run Notebook
```bash
jupyter notebook SAM2_Object_Tracking.ipynb
```

---

## 🧠 Tech Stack
- Python
- PyTorch
- NumPy / Pandas
- Matplotlib
- Segment Anything Model 2 (SAM2)

---

## 💡 Key Insights

### What Worked
- Large rigid objects tracked accurately
- Segmentation-based tracking effective
- Bounding box prompts improved initialization

### Challenges
- Small object tracking instability
- Performance drop under viewpoint change
- Some low IoU predictions need improvement

---

## 🔮 Future Improvements
- Temporal smoothing
- Better prompt strategies
- SAM2 fine-tuning
- Multi-object optimization
- Advanced memory-based tracking enhancements

---
