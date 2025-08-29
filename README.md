# 🧠 Automatic Image Captioning with Model Benchmarking and Robustness Analysis

## 📌 Overview
This project focuses on **Automatic Image Captioning** using a custom-built **Transformer-based Encoder-Decoder model**. It also benchmarks the custom model against the zero-shot performance of **SmolVLM**, evaluates robustness to **image occlusions**, and builds a **BERT-based classifier** to distinguish between captions from different models.

> 💡 Designed as part of CS60010 Deep Learning (Spring 2025), IIT Kharagpur.

---

## 📁 Project Structure

| Part | Title                                                                 | Description |
|------|-----------------------------------------------------------------------|-------------|
| A    | Custom Transformer-based Image Captioning                            | Implements and benchmarks a ViT-GPT2 encoder-decoder model for captioning |
| B    | Robustness Evaluation via Image Occlusion                            | Evaluates captioning model performance under 10%, 50%, 80% image masking |
| C    | Model Attribution via Caption Classification                         | Trains a BERT-based classifier to identify model origin from captions |

---

## 🛠️ Technologies Used

- **PyTorch**: Custom model development & training
- **HuggingFace Transformers**: Pre-trained ViT, GPT-2, BERT, SmolVLM
- **NLTK & HuggingFace Evaluate**: BLEU, METEOR, ROUGE-L, BERTScore
- **Google Colab**: Model training within 15GB GPU memory

---

## 🔍 Tasks Implemented

### ✅ Part A: Image Captioning Model

- Zero-shot captioning using [SmolVLM](https://huggingface.co/blog/smolvlm)
- Custom encoder-decoder model using:
  - Encoder: `ViT-Small-Patch16-224`
  - Decoder: `GPT-2 small`
- Evaluation metrics: **BLEU**, **ROUGE-L**, **METEOR**, **BERTScore**
- Compared performance with SmolVLM baseline

### ✅ Part B: Occlusion Robustness

- Occlusion simulation using random 16×16 patch masking (10%, 50%, 80%)
- Measured drop in captioning quality under occlusion for both models
- Reported performance deltas in BLEU, ROUGE-L, METEOR

### ✅ Part C: BERT-based Classification

- Input: `<original_caption> <SEP> <generated_caption> <SEP> <occlusion_level>`
- Model: `bert-base-uncased` + linear head for binary classification
- Trained to predict whether a caption came from SmolVLM or the custom model
- Evaluated on **macro precision, recall, F1**


Recommended environment:  
- Python 3.9+  
- GPU (NVIDIA T4 or better recommended)

---

## 🧪 Evaluation Metrics

- **Caption Quality**: BLEU, METEOR, ROUGE-L, BERTScore
- **Robustness**: Drop in captioning scores under patch occlusion
- **Classifier**: Precision, Recall, F1 (macro)

---

## 📚 References

- SmolVLM: https://huggingface.co/blog/smolvlm  
- ViT: https://huggingface.co/WinKawaks/vit-small-patch16-224  
- GPT-2: https://huggingface.co/gpt2  
- BERT: https://huggingface.co/google-bert/bert-base-uncased  
- METEOR: https://aclanthology.org/W05-0909  
- ROUGE-L: https://aclanthology.org/W04-1013  
