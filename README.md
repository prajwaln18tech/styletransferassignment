# 🖼️ Style Transfer

This project implements **Style Transfer** using PyTorch, inspired by the seminal work of **Gatys et al. (2016)**. The objective is to generate an image that combines the **content of one image** with the **style of another**, by optimizing a target image using feature maps extracted from a pretrained CNN.

## 📁 Project Structure

```
main/
├── Style_Transfer_Exercise_prajwal_narayanaswamy.ipynb           # Python script for neural style transfer
├── Style_Transfer_Exercise_prajwal_narayanaswamy.pdf    # Final report summarizing implementation and experiments
├── content.jpg              # Input content image
├── style.jpg                # Input style image
```

## 🚀 How It Works

- Loads a pretrained **VGG19** model (from torchvision).
- Extracts:
  - **Content features** from layer `conv4_2`
  - **Style features** from layers `conv1_1`, `conv2_1`, `conv3_1`, `conv4_1`, `conv5_1`
- Computes **Gram matrices** to represent style.
- Optimizes a target image using gradient descent to minimize a combined **content + style loss**:

```
Total Loss = α * Content Loss + β * Style Loss
```

## 🔧 How to Run

### 1. Install Dependencies

```bash
pip install torch torchvision matplotlib pillow
```

### 2. Run the Code

```bash
python Style_Transfer_Exercise_prajwal_narayanaswamy.ipynb
```

## 🧪 Experiments

Three experiments were conducted to explore the effect of different content and style weights:

| Experiment        | Content Weight (α) | Style Weight (β) | Final Loss   | Notes                      |
|------------------|--------------------|------------------|--------------|----------------------------|
| A - Balanced      | 1e5                | 1e2              | 5716.60      | Balanced mix               |
| B - More Style    | 1e5                | 1e4              | 118605.97    | Strong stylization         |
| C - More Content  | 1e3                | 1e2              | 1183.83      | Preserved structure        |

## 📄 Report

See `Style_Transfer_Exercise_prajwal_narayanaswamy.pdf` for:
- Implementation details
- Visual outputs
- Hyperparameter tuning results
- Key observations

## ✍️ Author

**Prajwal Narayanaswamy**  
MS in Computer Science  
California State University — Spring 2025


