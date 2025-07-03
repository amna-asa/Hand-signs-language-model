# Hand-signs-language-model

This project focuses on American Sign Language (ASL) hand gesture recognition using several popular deep learning architectures in PyTorch. The models are trained on a 29-class dataset (A–Z, 'del', 'nothing', 'space') using transfer learning techniques.

## 🔍 Models Trained
The following pre-trained models were fine-tuned:
- **AlexNet**
- **VGG16**
- **GoogLeNet**
- **Vision Transformer (ViT-B/16)**

## 📁 Dataset

We use the official **ASL Alphabet dataset** from Kaggle by *grassknoted*, which contains ~87,000 labeled images categorized into 29 classes (A–Z, del, nothing, space):  
📦 [ASL Alphabet Dataset – Kaggle](https://www.kaggle.com/datasets/grassknoted/asl-alphabet)


## ⚙️ Key Features

- Data Augmentation: Random horizontal flips, rotations
- Image Normalization using ImageNet mean/std
- Transfer Learning with layer freezing & fine-tuning
- Learning Rate Scheduler (`ReduceLROnPlateau`)
- Early stopping based on validation loss
- Graph generation for accuracy/loss
- Confusion matrix visualization

## 🧠 Transfer Learning Details

| Model      | Layers Unfrozen     | Pretrained on | Fine-tuned Layers         |
|------------|---------------------|---------------|---------------------------|
| AlexNet    | Classifier only     | ImageNet      | `classifier[-1]`          |
| VGG16      | Classifier only     | ImageNet      | `classifier[-1]`          |
| GoogLeNet  | FC layer only       | ImageNet      | `fc`                      |
| ViT-B/16   | Head initially      | ImageNet      | `heads.head` → full model |

## 📈 Results Summary

> 🔽 Replace the values below with actual numbers after training.

| Model      | Validation Accuracy | Best Val Loss |
|------------|---------------------|---------------|
| **AlexNet**    | ✅ 99.98%             | 📉 0.02%         |
| **VGG16**      | ✅ 3.39%              | 📉 96.61%        |
| **GoogLeNet**  | ✅ 100.0%             | 📉 0.00%         |
| **ViT-B/16**   | ✅ 99.91%             | 📉 0.09%         |



