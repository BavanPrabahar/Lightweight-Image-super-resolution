# Lightweight Image Super-Resolution

Welcome to the **Lightweight Image Super-Resolution** repository! This project provides a computationally efficient deep learning model designed to upscale low-resolution images by a factor of 3x. The architecture is primarily built to enhance photographs of people and is implemented using TensorFlow and Keras.

## 🚀 Key Features

- **3x Upscaling:** Enhances images from `170x170` to `510x510` pixels using sub-pixel convolution (`depth_to_space`).
- **Lightweight Architecture:** Uses a custom configuration of Interconnected Residual Blocks to maintain a low parameter count (~121K parameters) while achieving high structural similarity (MS-SSIM).
- **Efficient Inference:** Because of the small size of the model, inference is fast and highly suitable for resource-constrained environments.

## 📂 Repository Structure

- **[`Articles and blogs/`](Articles%20and%20blogs/)**: Contains links and references to articles explaining the model's architectural design and training process.
- **[`Dataset/`](Dataset/)**: Includes links to the dataset (sourced from Kaggle) used to train the model.
- **[`Model/`](Model/)**: Contains the pre-trained Keras model weights (`.h5` file) which can be directly loaded for inference.
- **[`Notebook/`](Notebook/)**: Contains the Jupyter notebook detailing data preprocessing, model building, and the training loop.

## 🛠 Model Architecture

The network processes an input tensor of shape `(170, 170, 3)` through interconnected Residual Blocks, each utilizing 32 filters. After feature extraction, a `depth_to_space` operation with a block size of 3 is applied to spatially upscale the feature maps to `(510, 510, 3)`. The optimization leverages a combined loss function of Mean Squared Error (MSE) and Multi-Scale Structural Similarity Index Measure (MS-SSIM).

## 🧠 Dataset

The model was trained on the [img-superres](https://www.kaggle.com/datasets/jagan028/img-superres) dataset from Kaggle. More details and the direct download link can be found in `Dataset/Dataset_link.txt`.

## 💻 Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/BavanPrabahar/Lightweight-Image-super-resolution.git
   cd Lightweight-Image-super-resolution
   ```
2. **Install Dependencies:** Ensure you have the required libraries installed, primarily `tensorflow`, `numpy`, `matplotlib`, and `Pillow`.
3. **Explore the Code:** Open the Jupyter Notebook in the `Notebook/` directory to see the step-by-step implementation.
4. **Run Inference:** Use the pre-trained `.h5` model weights located in the `Model/` directory to run image super-resolution on your own low-resolution inputs.
