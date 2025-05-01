# 🎙️ Speech Emotion Recognition (SER) with Hybrid Acoustic & Textual Analysis

This project is a full pipeline implementation of Speech Emotion Recognition (SER), combining both **acoustic-based emotion detection** using a custom-trained CNN model and **text-based emotion detection** using **Google's FLAN-T5** large language model.

The application includes:
- Data preparation, feature extraction, and training of an acoustic SER model.
- A GUI-based tool built with `Tkinter` that records user speech, transcribes it, and predicts emotions using both the acoustic model and the transcribed text.
- A reproducible environment using `conda`.

---

## 🧠 Project Overview

This repo contains two Jupyter Notebooks:

### 1. `Speech-emotion-recognition.ipynb`
A full machine learning pipeline for **acoustic-based emotion recognition**:
- 📥 Loads and preprocesses audio datasets.
- 🎛️ Extracts audio features (MFCCs, Chroma, ZCR, RMS, etc.).
- 🧠 Trains a CNN-based model to classify emotions from speech.
- 📊 Visualizes training performance (loss, accuracy, confusion matrix).

### 2. `Pipelined.ipynb`
A working demo app using `Tkinter`:
- 🎙️ Records live audio from your mic.
- 🧾 Transcribes the audio using a speech recognition engine.
- 🧠 Predicts emotion from audio using the trained CNN model.
- 🧠 Predicts emotion from transcribed text using the FLAN-T5 LLM.
- 🧾 Displays both sets of predictions for comparison.

---

## ⚙️ Installation & Setup

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
