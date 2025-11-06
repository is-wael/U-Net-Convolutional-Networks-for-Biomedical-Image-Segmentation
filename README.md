# 🧬 U-Net : Segmentation d'Images Biomédicales

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://www.tensorflow.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/VOTRE_USERNAME/VOTRE_REPO/blob/main/Unet.ipynb)

> Implémentation de l'architecture U-Net pour la segmentation d'images d'échographie mammaire (Dataset BUSI)

---

## 📋 Table des Matières

- [À Propos](#à-propos)
- [Architecture](#architecture)
- [Dataset](#dataset)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Résultats](#résultats)
- [Structure du Projet](#structure-du-projet)
- [Références](#références)
- [Auteur](#auteur)

---

## 🎯 À Propos

Ce projet implémente l'architecture **U-Net** proposée par Ronneberger et al. (2015) pour la **segmentation sémantique d'images biomédicales**. Le modèle est entraîné sur le dataset **BUSI** (Breast Ultrasound Images) pour détecter et segmenter automatiquement les masses tumorales dans les échographies mammaires.

### Caractéristiques Principales

- ✅ Architecture U-Net complète avec **7,696,193 paramètres**
- ✅ Entraînement avec et **sans augmentation de données**
- ✅ Résolution d'entrée : **128×128 pixels**
- ✅ Segmentation binaire (tumeur/fond)
- ✅ Notebook interactif Google Colab
- ✅ Visualisation comparative des résultats

---

## 🏗️ Architecture

L'architecture U-Net se compose de deux parties principales :

### Chemin Contractant (Encoder)
- 4 blocs de convolution (64 → 128 → 256 → 512 filtres)
- Convolutions 3×3 suivies de ReLU
- Max-pooling 2×2 pour le sous-échantillonnage

### Chemin Expansif (Decoder)
- 4 blocs d'up-sampling avec skip connections
- Conv2DTranspose pour l'upsampling
- Concaténation avec les features du chemin contractant
- Convolution finale 1×1 avec activation sigmoid

![Architecture U-Net](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/u-net-architecture.png)

**Total Parameters:** 7,696,193 (29.36 MB)

---

## 📊 Dataset

### BUSI (Breast Ultrasound Images Dataset)

- **Source** : Dataset public disponible sur Kaggle
- **Composition** :
  - 🟢 Normal : 133 images
  - 🔵 Benign : 437 images  
  - 🔴 Malignant : 210 images
  - **Total** : 780 images + masques de segmentation

- **Prétraitement** :
  - Redimensionnement : 128×128 pixels
  - Normalisation : [0, 1]
  - Split : 90% train / 10% validation
  - Conversion en niveaux de gris

---

## 🚀 Installation

### Prérequis

