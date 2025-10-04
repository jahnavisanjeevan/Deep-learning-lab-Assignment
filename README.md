# Deep-learning-lab-Assignment
# Deep Learning Lab Assignment

This repository contains my submission for the Deep Learning Lab assignment.

---

## 📂 Contents
- `q1.ipynb` — Vision Transformer (ViT) on CIFAR-10 (PyTorch)
- `q2.ipynb` — Text-driven Image Segmentation with SAM 2
- `README.md` — Instructions, model details, and results

---

## 🧠 Q1 — Vision Transformer on CIFAR-10

**Goal:** Implement a ViT from scratch and train it on CIFAR-10 (10 classes).  
**Reference Paper:** *An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale (Dosovitskiy et al., 2021)*

### ✅ Implementation Steps
1. Patchify images and linearly project flattened patches.
2. Add learnable positional embeddings.
3. Prepend a learnable CLS token.
4. Stack Transformer encoder blocks (MHSA + MLP + residual + norm).
5. Classify using the CLS token.

### ⚙️ Best Model Configuration
| Parameter | Value |
|------------|--------|
| Patch Size | 4 |
| Embedding Dim | 256 |
| Depth | 8 |
| Heads | 4 |
| Batch Size | 128 |
| Optimizer | AdamW |
| Learning Rate | 1e-3 |
| Scheduler | CosineAnnealing |
| Epochs | 100 |

### 🧾 Results
| Metric | Value |
|--------|--------|
| Test Accuracy (%) | 87.5 |

### 🔍 Bonus Analysis
Smaller patches (4×4) improved accuracy but required more computation.  
Using Mixup & RandAugment boosted performance by ~2%.

---

## 🎨 Q2 — Text-Driven Image Segmentation with SAM 2

**Goal:** Perform text-prompted segmentation of objects in an image using SAM 2.

### ✅ Implementation Steps
1. Load image and text prompt.
2. Convert text to region seeds using `GroundingDINO` or `CLIPSeg`.
3. Feed seeds into `SAM 2` to generate segmentation mask.
4. Display mask overlay on the image.

### ⚙️ Example
**Input Text:** `"segment the cat"`  
**Output:** Mask highlighting the cat region.

### ⚠️ Limitations
- Requires large checkpoints (~1–2 GB).
- Inference speed depends on GPU memory.
- Text-seed quality varies by model.

---

## 🧩 How to Run
1. Open in Google Colab.
2. Set Runtime → Change runtime type → GPU.
3. Run all cells (top to bottom).
4. `q1.ipynb` trains ViT and prints final accuracy.
5. `q2.ipynb` visualizes segmentation results.

---

## 🧠 Author
**Name:** Jahnavi  
**Program:** B.Tech CSE (AIML) — Mohan Babu University  
