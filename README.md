# 🎙️ Speech Emotion Recognition (SER) with Hybrid Acoustic & Textual Analysis

This project is a full pipeline implementation of Speech Emotion Recognition (SER), combining both **acoustic-based emotion detection** using a custom-trained CNN model and **text-based emotion detection** using **Google's FLAN-T5** large language model.

The application includes:
- Data preparation, feature extraction, and training of an acoustic SER model.
- A GUI-based tool built with `Tkinter` that records user speech, transcribes it, and predicts emotions using both the acoustic model and the transcribed text.
- A reproducible environment using `conda`.

---

## 📂 Datasets Used

This project uses a combination of four widely used emotion speech datasets to improve model generalization and emotion coverage:

### 🎼 RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song)
- 24 actors (12 male, 12 female) vocalizing two statements with 8 emotions.
- High-quality audio recordings (.wav, 48kHz).
- 📎 [Download RAVDESS](https://zenodo.org/record/1188976)

### 🗣️ TESS (Toronto Emotional Speech Set)
- 2 female speakers, age 26 and 64.
- 200 target words spoken in 7 emotions (excluding "disgust").
- Sample rate: 16kHz.
- 📎 [Download TESS](https://tspace.library.utoronto.ca/handle/1807/24487)

### 😠 SAVEE (Surrey Audio-Visual Expressed Emotion)
- Male British speakers only.
- 7 emotions across 480 utterances.
- Good for gender diversity in training sets.
- 📎 [Download SAVEE](https://zenodo.org/record/1188976) *(Note: may require request)*

### 🎭 CREMA-D (Crowd-sourced Emotional Multimodal Actors Dataset)
- 91 actors (48 male, 43 female), multiple ethnicities.
- 7 emotions: anger, disgust, fear, happy, neutral, sad, surprise.
- Over 7,000 clips.
- 📎 [Download CREMA-D](https://github.com/CheyneyComputerScience/CREMA-D)

---
## 🧠 Hybrid Inference Pipeline
This project follows a two-path pipeline:

1. 🔊 Acoustic Emotion Recognition
Audio → Feature Extraction (MFCC, Chroma, etc.)

→ Trained CNN Model

→ Emotion Output (based on tone and audio)

2. 📝 Text-Based Emotion Recognition
Audio → Parakeet ASR 110M → Transcription

Transcribed Text → FLAN-T5 (fine-tuned LLM) → Emotion Output (based on content)

### 🎯 Final output compares both to help validate and cross-check emotion detection accuracy.

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
A Tkinter GUI app that:
- 🎙️ Records live audio and saves it.
- 🧠 Uses **NVIDIA’s Parakeet ASR 110M** model for **offline speech transcription**.
- 🧠 Predicts emotion from raw audio using the trained CNN SER model.
- 🧠 Predicts emotion from transcribed text using **Google’s FLAN-T5** model.
- 📋 Outputs both results to show how emotion is detected acoustically and textually.

> This hybrid architecture helps validate emotion prediction from both audio tone **and** speech content.

> The project is focused for running on Windows. If you want to run this on a linux or WSL, The following link is guided to the same project but built on WSL so the requirements are matching the kernel.

---

## ⚙️ Installation & Setup

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name

2. Create the environment file using the yml file:
  ```bash
   conda env create -f environment.yml
```
---

## 📚 References

This project builds upon and is inspired by the following works and open-source tools:
- Shivam Burnwal's Kaggle notebook. (https://www.kaggle.com/code/shivamburnwal/speech-emotion-recognition)
This notebook has been a base for building the SER model and improving on it. 

---

## 💡 Author

Made with ☕, Valorant rage-quits, and dreams of being an ML engineer
Harshal — just a student trying to turn failure into functional code.
