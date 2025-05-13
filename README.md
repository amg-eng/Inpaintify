# 🖼️ Inpaintify: Deep Learning-Based Generative Image Inpainting with Contextual Attention

## 📌 Overview

**Inpaintify** is a deep generative image inpainting project that utilizes a two-stage convolutional neural network augmented with a **contextual attention mechanism**. Our model effectively fills in missing regions in images with high structural and textural coherence. We trained and evaluated the model on **CelebA-HQ** and **DIV2K** datasets.

This project combines **coarse reconstruction** and **refinement** using contextual attention to synthesize semantically consistent outputs. It is especially effective at object removal, watermark elimination, and image restoration tasks.


## 📄 Paper

You can read our full research paper [here](https://drive.google.com/file/d/1Jk3LVC8SoQeQT319EJn5BremGpKRf3_U/view?usp=sharing).

## 🧠 Core Contributions

- A **two-stage encoder-decoder architecture** with dilated convolutions for coarse estimation.
- A **contextual attention module** for referencing distant known image regions during refinement.
- Use of **Wasserstein GAN with gradient penalty** (WGAN-GP) for adversarial training.
- Evaluation on **CelebA-HQ** (faces) and **DIV2K** (natural scenes) datasets.
- Achieves high-quality and visually plausible results, outperforming traditional patch-based and CNN-only models.


## 🧪 Demo

> Sample output of our inpainting model (CelebA-HQ & DIV2K):
<p align="center">
  <img src="assets/Picture5.jpg" alt="Inpainting Result" width="700"/>
</p>


## 📈 Methodology

### 1. **Coarse Stage**  
Encoder-decoder architecture with **dilated convolutions** generates a rough prediction.
<p align="center">
  <img src="assets/Picture4.png" alt="Corase" width="700"/>
</p>

### 2. **Refinement Stage**  
Employs **contextual attention** to match known patches with missing areas and enhance realism.
<p align="center">
  <img src="assets/Picture3.png" alt="Refinement" width="700"/>
</p>


### 3. **Loss Functions**

- **L1 Reconstruction Loss**
- **WGAN-GP Adversarial Loss**
- **Spatially Discounted Loss**

### 🔍 Attention Calculation

Cosine similarity is used to compute attention between patches. A softmax function normalizes attention weights for aggregation.

## 📊 Datasets

- **CelebA-HQ** (30,000 facial images)
- **DIV2K** (1,000 diverse natural images)
<p align="center">
  <img src="assets/Picture1.png" alt="Dataset" width="700"/>
  <br/>
  <img src="assets/Picture2.jpg" alt="Masks" width="700"/>
</p>

> All images were resized to **256x256**, and random rectangular binary masks (10%–40% area) were applied.


## ⚙️ Setup & Requirements

### 🔧 Installation

```bash
git clone https://github.com/<your-username>/Inpaintify.git
cd Inpaintify
pip install -r requirements.txt
```

### 🧾 Requirements

```bash
tensorflow
numpy
matplotlib
opencv-python
tqdm
```

## 🚀 Usage
▶️ Run Notebook
You can open and run `Inpaintify.ipynb` directly in Google Colab or Jupyter Notebook.

### 📌 Steps:
1. Load and preprocess datasets.
2. Generate binary masks.
3. Train the model.
4. Visualize inpainted results.


## 📊 Results

- High quality inpainting for small to medium-sized masks.
- Artifacts and inconsistencies for very large masked regions due to model limitations.
- Faster and more stable compared to baseline methods.
- See detailed results in the notebook and paper.

## 📉 Limitations

- Reduced performance for very large or complex masks.
- Training time and memory usage increase with image resolution.
- Limited epochs due to hardware constraints.

## 👥 Contributing
<p align="center">
  Made with ❤️ by Team Inpaintify
</p>
<table align="center">
  <tr align="center">
      <td align="center">
      <a href="https://github.com/Ziyad-HF" target="_black">
      <img src="https://avatars.githubusercontent.com/u/99608059?v=4" width="150px;" alt="Ziyad El Fayoumy"/>
      <br />
      <sub><b>Ziyad El Fayoumy</b></sub></a>
      </td>
      <td align="center">
      <a href="https://github.com/AbdulrahmanGhitani" target="_black">
      <img src="https://avatars.githubusercontent.com/u/114954706?v=4" width="150px;" alt="Abdulrahman Shawky"/>
      <br />
      <sub><b>Abdulrahman Shawky</b></sub></a>
      </td>
      <td align="center">
      <a href="https://github.com/amg-eng" target="_black">
      <img src="https://avatars.githubusercontent.com/u/101107538?v=4" width="150px;" alt="amgad"/>
      <br />
      <sub><b>Amgad Atef</b></sub></a>
      </td>
      <td align="center">
      <a href="https://github.com/ahmadMfouad" target="_black">
      <img src="https://avatars.githubusercontent.com/u/104557512?v=4" width="150px;" alt="ahmad"/>
      <br />
      <sub><b>Ahmad Mahmoud</b></sub></a>
      </td>
    </tr>
 </table>

---
