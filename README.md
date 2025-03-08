# Liver Segmentation using Half U-Net

## Project Description
This project focuses on an improved liver segmentation model using **Half U-Net**, achieving:
- **89.6% Intersection over Union (IOU)**
- **87.4% Dice Coefficient**

To enhance model performance, multiple loss functions were explored:
- Dice Loss
- Binary Cross-Entropy (BCE) Loss
- Hybrid Loss
- K Loss

## Project Structure
```
.
├── Half_Unet_Liver.ipynb        # Jupyter Notebook with model code
├── Results                      # Folder containing model results
│   ├── Metrics.txt              # Performance metrics (IOU, Dice, etc.)
│   ├── Predicted_Images         # Folder with segmented images
│   ├── Ground_Truth_Images      # Folder with ground truth masks
├── Dataset                      # Folder containing input data and labels
│   ├── images/                  # Input images (X)
│   ├── masks/                   # Corresponding segmentation masks (Y)
└── requirements.txt              # Required dependencies
```

## About the Dataset
The dataset consists of liver images where each pixel is labeled to indicate specific liver regions. The segmentation masks help in training a deep learning model to distinguish between liver structures.

- Data is provided in **NIfTI format** (Neuroimaging Informatics Technology Initiative).
- Each input image is paired with a **ground truth mask**.
- The dataset is crucial for **computer-aided liver disease diagnosis** and **medical image analysis**.

## Implementation Steps
### 1. Install Dependencies
Ensure you have **Python 3.10** installed. Verify **pip** installation and upgrade if needed:
```sh
pip --version
python3.10 -m pip install --upgrade pip
```

Install the required dependencies:
```sh
pip install -r requirements.txt
```

### 2. Setup Dataset
- Organize the dataset as mentioned in the **Project Structure**.
- If the dataset is missing, it will be **automatically downloaded** when running the notebook.

### 3. Run the Jupyter Notebook
Launch the Jupyter Notebook and execute **Half_Unet_Liver.ipynb**:
```sh
jupyter notebook Half_Unet_Liver.ipynb
```

## Half U-Net Architecture
**Half U-Net** is a **lightweight** variation of the traditional **U-Net** designed for medical image segmentation.

### Key Features:
- **Encoder-Decoder Structure:** Retains the core U-Net design with a contracting (encoder) and expanding (decoder) path.
- **Unification of Channel Numbers:** Standardized feature channels reduce computational complexity.
- **Full-Scale Feature Fusion:** Merges multi-scale features for better segmentation performance.
- **Ghost Modules:** Reduces parameters and FLOPs while preserving feature extraction efficiency.

### Advantages of Half U-Net:
- **Accuracy:** Matches U-Net’s segmentation accuracy while being computationally efficient.
- **Efficiency:**
  - **98.6% parameter reduction** compared to standard U-Net.
  - **81.8% fewer floating-point operations (FLOPs)**.

### Loss Functions Used
To optimize the segmentation performance, multiple loss functions were explored:
- **Dice Loss:** Optimizes the overlap between predicted and ground truth masks.
- **Binary Cross-Entropy (BCE) Loss:** Measures pixel-wise classification performance.
- **Hybrid Loss:** Combines Dice and BCE for improved gradient flow.
- **K Loss:** Custom loss function tailored for specific segmentation challenges.

## Results & Performance
- **IOU Score:** 89.6%
- **Dice Coefficient:** 87.4%
- **Parameter Reduction:** 98.6% fewer parameters than standard U-Net.
- **Computation Reduction:** 81.8% fewer FLOPs, making it faster and memory-efficient.

## Conclusion
This project demonstrates that **Half U-Net** provides a **lightweight, computationally efficient** solution for **medical image segmentation** while maintaining accuracy comparable to traditional U-Net models.

---
📌 **Future Enhancements:**
- Fine-tuning the model on larger liver segmentation datasets.
- Experimenting with different data augmentation techniques.
- Deploying the model using Flask/Streamlit for real-time segmentation.

🚀 **Contributions Welcome!** If you have suggestions for improving the model, feel free to fork the repo and submit a pull request.

