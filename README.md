# Plant Disease Explainer 

An interpretable computer vision project that takes a plant leaf image 

- predicts the **plant–disease class**
- generates a **Turkish natural-language explanation** of the diagnosis
- also visualizing where the model is looking via Grad-CAM

This repository contains the code for the project  
**“Bitki Görüntüleri İçin Yorumlanabilir Hastalık Açıklama Modeli”**,  
developed as part of the *Computer Vision (BLM5103)* course at Yildiz Technical University.

---

## Features

- **Plant disease classification**
  - Transfer learning with **ResNet-18** on the PlantVillage dataset
  - Test accuracy: ~**91.5%**
  - Test macro F1-score: ~**0.88**

- **Image-to-text disease explanation**
  - CNN encoder (ResNet-18) + LSTM decoder
  - For each plant–disease class, a Turkish symptom description template is defined
  - The model learns to generate these descriptions from images
  - Validation BLEU score: ~**0.95**

- **Interpretability via Grad-CAM**
  - Grad-CAM heatmaps over the input leaf images
  - Shows which regions the classifier focuses on when predicting the disease

- **Interactive demo (Gradio)**
  - Upload a leaf image
  - The system returns:
    - the predicted disease class (with a Turkish label),
    - the generated Turkish explanation sentence,
    - and a Grad-CAM heatmap overlay.

---

## Dataset

The project uses a PlantVillage-based dataset available on HuggingFace:

- **HuggingFace dataset:** `BrandonFors/Plant-Diseases-PlantVillage-Dataset`
- Contains:
  - ~54k leaf images
  - 38 classes (plant species + disease combinations)
- The dataset is automatically downloaded via the `datasets` library inside the notebook.
  You do **not** need to manually download it.

Please note:  
The dataset itself is subject to its **own original license and terms of use**.

---

## Project Structure

- `plant_diseases.ipynb` – Jupyter/Colab notebook containing:
  - dataset loading and preprocessing
  - training the ResNet-18 classifier
  - training the image-to-text (caption) model
  - Grad-CAM visualization code
  - Gradio demo interface

- `LICENSE` – MIT license for the code in this repository.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/iclalsonmez/plant-disease-explainer.git
cd plant-disease-explainer
```

Install the required packages (example):

```bash
pip install datasets gradio nltk matplotlib 
```

Then open the notebook:
plant_diseases.ipynb
and run the cells from top to bottom (or only the demo section if you just want to showcase the model).

## License

This project’s code is released under the MIT License:
The PlantVillage-based dataset used in this project is provided via HuggingFace
(BrandonFors/Plant-Diseases-PlantVillage-Dataset) and remains subject to its original license and terms of use.
