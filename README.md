## 🪪 ID Card Reader (YOLOv11 + PaddleOCR)

### 📘 Overview

The **ID Card Reader** is a computer vision project that automatically detects and reads information from various ID card types.
It was developed as an internal automation tool for **PT Apikko**, aiming to eliminate manual data entry errors by administrative staff.

Using **YOLOv11** for object detection and **PaddleOCR** for text recognition, this project can accurately identify card types and extract printed details directly from the image.

---

### 🎯 Objectives

The project was created to:

* Automate ID card data extraction.
* Reduce manual entry mistakes by staff.
* Standardize record-keeping for multiple ID formats.

---

### 🧠 Supported ID Card Types

The dataset consists of six card types obtained from PT Apikko:

1. Hong Kong Identity Card (v3)
2. Hong Kong Permanent Resident Card (v3)
3. Hong Kong Identity Card (v4)
4. Hong Kong Permanent Resident Card (v4)
5. Indonesian ID Card (KTP)
6. Indonesian Passport

---

### ⚙️ Technologies Used

| Component            | Description                                               |
| -------------------- | --------------------------------------------------------- |
| **YOLOv11**          | Used for ID card detection and localization.              |
| **PaddleOCR**        | Used for text extraction (Optical Character Recognition). |
| **Python**           | Main programming language.                                |
| **Jupyter Notebook** | Used for development and deployment.                      |
| **OpenCV**           | Image preprocessing and visualization.                    |

---

### 📁 Project Structure

```
IdCardPortfolio.ipynb   # Main notebook file
dataset/                 # Folder containing labeled ID card images
models/                  # YOLOv11 and PaddleOCR model files (if applicable)
outputs/                 # Example extracted results or logs
README.md                # Project documentation
```

---
### 🧩 Model Training & Preprocessing

#### 🏷️ Dataset Preparation

* Images of ID cards were provided by **PT Apikko**.
* Each image was labeled with bounding boxes corresponding to the ID card region using **Roboflow** or similar annotation tools.
* Dataset was split into:

  * **Train set:** 80%
  * **Validation set:** 10%
  * **Test set:** 10%

#### 🧰 Preprocessing Steps

* Image resizing and normalization to YOLOv11 input dimensions.
* Automatic augmentation (rotation, brightness, and cropping) to improve robustness.
* OCR preprocessing included:

  * Grayscale conversion
  * Noise reduction and thresholding
  * Region of Interest (ROI) extraction for clearer text recognition.

#### 🧠 Model Training

* **YOLOv11** was fine-tuned on the custom dataset for card detection.
* Training performed for multiple epochs until optimal mAP (mean average precision) was reached.
* **PaddleOCR** was used for text recognition after the card region was detected.
* OCR outputs were parsed and structured into readable formats (name, ID number, address, etc.).

#### Open the notebook

```bash
jupyter notebook IdCardPortfolio.ipynb
```

#### 4. Run all cells

The notebook will:

* Detect the ID card in the image.
* Perform OCR extraction.
* Print the extracted information in the output cell.

---


### 🧩 Future Improvements

* Export OCR results to CSV or JSON format.
* Build a user-friendly interface using Streamlit or Flask.
* Support for more ID types and languages.
* Enhance accuracy with fine-tuned models.

---

### 👩‍💼 Acknowledgements

Special thanks to **PT Apikko** for providing the dataset and project request.
Developed by **Lukita Iswara** as part of internal automation efforts.


