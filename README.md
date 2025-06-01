# English–Vietnamese Neural Machine Translation

**Capstone Project - IT4772E: Natural Language Processing**

Lecturer: [Assoc. Prof. Lê Thanh Hương](https://soict.hust.edu.vn/pgs-ts-le-thanh-huong.html)

Date: May 2025 - Semester 20242 - HUST


## 📌 Overview

This project explores and compares 2 different neural machine translation (NMT) architectures for the English → Vietnamese task:
- **Seq2Seq with Bahdanau Attention** – implemented from scratch using bidirectional LSTMs.

- **Fine-tuned MarianMT** – a pretrained Transformer model adapted to the PhoMT dataset.

The goal is to evaluate how different modeling philosophies perform under a shared evaluation framework, both quantitatively (BLEU) and qualitatively (manual translation analysis).


## 🗂️ Project Structure
**1. Seq2seq + Bahdanau Attention**

This model was trained locally. For the dataset, please follow this [link](https://docs.google.com/forms/d/e/1FAIpQLSfShfLzQ3w9ErBc6sId55s83o9tOv2qz6zMd_6lNCD7n791NQ/viewform) to download the PhoMT dataset. We used the detokenization folder for this project. Note that we used the PhoMT dataset for our educational purposes only.

```bash
  PhoMT/
  ├─ seq2seq_lstm_attention_beam_search.ipynb
  ├─ prepare.ipynb # run this file to convert raw dataset to .json format (this is actually related to marianmt, but I leverage this folder due to the available raw dataset for converting :D)
  ├─ detokenization/
  │  ├─ train/
  │  │  ├─ train.en
  │  │  ├─ train.vi
  │  ├─ dev/
  │  │  ├─ dev.en
  │  │  ├─ dev.vi
  │  ├─ test/
  │  │  ├─ test.en
  │  │  ├─ test.vi

```

**2. Finetuned MarianMT**

This model was trained on Google Colab. For the dataset, we combined the raw text files 
```.en``` and ```.vi``` and convert it to the ```json``` format for MarianMT, by running the ```prepare.ipynb``` in the previous workspace. You can directly download the dataset file ```phomt_cleaned.json``` in this [link](https://drive.google.com/file/d/1z0QBWRpmLqYP8RdaKgQf0HokNGsP1l36/view?usp=sharing). Then easily copy it to your own workspace, in the same folder with ```marianmt.ipynb```.

```bash
  content/
  ├─ drive/
  │  ├─ MyDrive/
  │  │  ├─ IT4772E - NLP/
  │  │  │  ├─ marianmt/
  │  │  │  │  ├─ marianmt.ipynb
  │  │  │  │  ├─ phomt_cleaned.json

```

**3. GUI**

This section illustrates our workspace for running the GUI, which was separately implemented on Google Drive and Colab. You can find the checkpoint for both 2 models here: [MarianMT](https://drive.google.com/drive/folders/11zhhg9uWp-tcVQbZCITEZrywwpTg1_7p?usp=sharing), [Seq2seq](https://drive.google.com/file/d/1Eh5dsVSC755ClQPwnUWgJZnuB86EEAhN/view?usp=sharing).

```bash
  content/
  ├─ drive/
  │  ├─ MyDrive/
  │  │  ├─ IT4772E - NLP/
  │  │  │  ├─ marianmt/
  │  │  │  │  ├─ marian_finetuned_vi_final/ # marianmt checkpoint
  │  │  │  │  ├─ best_model.pt # seq2seq checkpoint
  │  │  │  │  ├─ GUI_marianmt_seq2seq.ipynb

```

## 🚀 How to Run
Clone my repo:
```bash
git clone https://github.com/teddydog23/MachineTranslation.git
```
**1. Seq2seq + Bahdanau Attention**

Download the dataset PhoMT, copy ```seq2seq_lstm_attention_beam_search.ipynb``` and ```requirements.txt``` in my ```seq2seq``` branch to your workspace. Just mimic my workspace to avoid any trouble with refactoring.

Ensure full environment setup before running ```seq2seq_lstm_attention_beam_search.ipynb```:

```bash
pip install -r requirements.txt
```

**2. Finetuned MarianMT**

Download the dataset (```.json``` file), simulate my Colab workspace, run ```marianmt.ipynb```.

**3. GUI**

Run ```GUI_marianmt_seq2seq.ipynb``` and test with some English sentences.
