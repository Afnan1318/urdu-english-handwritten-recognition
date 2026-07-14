# Multilingual Handwriting Recognition (Urdu & English)
**Authors:** Afnan Ijaz & Hasnain Sherazi
*BS Artificial Intelligence — Machine Learning Course Project*

---

## Project Overview
A deep learning system that recognizes single handwritten characters and digits in Urdu and 
English, with automatic language detection and an interactive web demo built with Gradio.

**Tech stack:** Python · PyTorch · OpenCV · Gradio

---

## Features
- Shared CNN encoder with two classification heads (Urdu, English) and a language-detection head
- Handles full Urdu alphabet (Arabic-script Unicode) + Urdu digits, and full English alphabet + digits
- Unknown-input rejection — flags non-Urdu/English inputs (e.g. CJK script)
- Multi-character detection — warns if more than one character is in the uploaded image
- Interactive Gradio web UI with live confidence bars

---

## Model Architecture
- Shared Encoder: 4-block CNN (32→64→128→256 channels) → 256-dim feature vector
- Language Head: Urdu / English / Unknown
- Character Heads: separate heads per language on the shared feature space

| Task | Accuracy |
|---|---|
| Urdu character recognition | 88.3% |
| English character recognition | 97.9% |
| Language detection | 99.6% |
| Unknown rejection | 99.7% |

---

## How to Run
1. `pip install -r requirements.txt`
2. `python app.py`
3. Open the local Gradio URL, upload one handwritten character at a time
