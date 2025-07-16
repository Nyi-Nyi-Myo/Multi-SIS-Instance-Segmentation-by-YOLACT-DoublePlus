# Multi-SIS-Instance-Segmentation-by-YOLACT++

This repository contains code and results for **instance segmentation** of surgical instruments using **YOLACT++ (ResNet-50)** on a custom dataset.

## 🗂 Dataset

- **Format:** COCO-style (JSON)
- **Classes (6):**
  - Grasper
  - Harmonic_Ace
  - Myoma_Screw
  - Needle_Holder
  - Suction
  - Trocar
- **Folders:**
  - `images/train/`, `images/valid/`
  - `annotations/instances_train.json`, `instances_valid.json`

## 🏗 Model & Training

- **Model:** `mask_rcnn_R_101_FPN_3x.yaml`
- **Backbone:** ResNet-101 + FPN
- **Epochs:** 30
- **Framework:** Detectron2
- **Score Threshold:** 0.7
- **NMS Threshold:** 0.4

### 💡 Evaluation

**Bounding Box (bbox):**
- mAP@[0.50:0.95]: `67.6%`
- AP50: `83.4%`
- Best class: `Trocar` (77.9%), `Harmonic_Ace` (75.9%)
- Worst class: `Suction` (50.6%)

**Segmentation (segm):**
- mAP@[0.50:0.95]: `65.9%`
- AP50: `83.9%`
- Best class: `Trocar` (80.1%)
- Worst class: `Suction` (50.1%)

## 🔍 Inference

To run inference and visualize N random samples from validation set:

```python
run_inference_on_random_images(num_images=12)
```

- Colors are fixed per class
- Results shown in 4-column grid

📌 Example:

![Example Results](./YOLACT++_results_sample.png)

## 📦 Files

- `.ipynb` – Step by step codes
- `.png` – Example results
- `README.md` – You are here

## ⚙ Dependencies

- Python 3.11
- PyTorch
- Detectron2

## 📜 License

This project is released for research purposes only. Please cite appropriately if used in publications.
