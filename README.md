# Multilayer Perceptrons for Image Classification

**Team:** Jack Parry-Wingfield, Lucas Andrade, Alina Shimizu-Jozi  

## Overview

This project explores the effectiveness of Multilayer Perceptrons (MLPs) for image classification on the **Kuzushiji-MNIST** dataset. We implemented an MLP, experimented with depth, activation functions, and regularization; then compared results to a Convolutional Neural Network (CNN) implemented using PyTorch.

Spoiler: CNNs still win when it comes to vision tasks, but our custom-built MLPs held their own and delivered surprisingly competitive results.

## Collaborators  

This project was developed by:

- **Jack Parry-Wingfield** - [GitHub Profile](https://github.com/JackPW-lang)  
- **Alina Shimizu** - [GitHub Profile](https://github.com/alinashimizu)  
- **Lucas Andrade** - [GitHub Profile](https://github.com/lucasandrdd)  

**LaTeX Documentation**: You can find the detailed documentation [here](MLDocumentation1.pdf) 

---

## Dataset

- **Name:** Kuzushiji-MNIST (KMNIST)  
- **Size:** 70,000 grayscale images (28×28 pixels)  
- **Classes:** 10 Japanese character categories  
- **Train/Test Split:** 60k train / 10k test  
- **Preprocessing:**  
  - Flattened images to 784-dim vectors  
  - Standardized features  

---

## Model Architectures

### MLP (Implemented from Scratch)
- Fully connected layers
- ReLU, Leaky ReLU, and Sigmoid activations tested
- Single and double hidden-layer variants
- Manual backpropagation and weight updates
- L1 and L2 regularization options

### CNN (PyTorch)
- Conv2D layers with ReLU activations
- MaxPooling
- Fully connected head
- Used as a baseline comparison

---

## Experiments & Findings

| Experiment | Summary |
|-----------|---------|
| **Depth vs Accuracy** | 2-layer MLPs performed better than single-layer and no-layer models. |
| **Activation Functions** | ReLU > Leaky ReLU > Sigmoid (ReLU hit 90.6% test accuracy). |
| **L2 Regularization** | Optimal λ = 0.001 — test accuracy ~88.6%. |
| **L1 Regularization** | Overly strong λ killed accuracy, best test score was 90.55%. |
| **CNN Performance** | CNN with 128 hidden units hit **94.33% test accuracy** — top score. |
| **Overfitting Watch** | Bigger isn't always better — 128 units outperformed 256 in test acc. |

---

## Results (MLP vs CNN)

| Model                  | Validation Accuracy | Test Accuracy |
|------------------------|---------------------|----------------|
| No Hidden Layer MLP    | 0.6176              | 0.6176         |
| 1-Layer MLP (256 units)| 0.9213              | 0.8373         |
| 2-Layer MLP (256 units)| 0.9560              | 0.8914         |
| 2-Layer MLP (128 units)| **0.9793**          | 0.9433         |
| CNN (128 hidden units) | **0.9793**          | **0.9433**     |

---

## How to Run
