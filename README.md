# English-to-Hindi Neural Machine Translation (Transformer from Scratch) 🇬🇧 ➡️ 🇮🇳

## 📌 Overview
This repository contains a sequence-to-sequence Transformer model built completely from scratch to translate text from English to Hindi. Instead of relying on pre-built high-level library implementations, this project constructs the core Transformer architecture (Self-Attention, Multi-Head Attention, Encoder, and Decoder blocks) from the ground up to deeply understand the mechanics of modern Large Language Models.

## 🚀 Features
* **Custom Transformer Architecture:** Full implementation of the architecture described in *Attention Is All You Need*.
* **Autoregressive Decoding:** Custom token-by-token generation with temperature scaling to control prediction randomness.
* **Minimum Bayes Risk (MBR) Decoding:** Advanced decoding strategy that generates multiple candidate translations and selects the one with the highest expected similarity to the reference.
* **Comprehensive Evaluation:** Built-in translation evaluation using custom-configured **BLEU** (NLTK) and **ROUGE** metrics to accurately score Hindi text generation.

## 🛠️ Tech Stack
* **Language:** Python
* **Deep Learning:** TensorFlow / Keras (or PyTorch - *Update depending on your exact framework*)
* **NLP Processing:** NLTK, Rouge
* **Data Manipulation:** NumPy, Pandas

## 🧠 Model Architecture
The model relies on a standard encoder-decoder Transformer structure:
1. **Input Embedding & Positional Encoding:** Converts English and Hindi tokens into dense vectors and injects sequence order information.
2. **Encoder Blocks:** Multiple layers of Multi-Head Self-Attention and Feed-Forward networks to build contextual representations of the English input.
3. **Decoder Blocks:** Masked Multi-Head Attention to prevent future token lookahead, followed by Cross-Attention over the Encoder's output.
4. **Output Layer:** A dense linear layer with Softmax activation to predict the probability distribution of the next Hindi token in the sequence.

## 📊 Evaluation Metrics
Because Hindi sentence structure can be flexible, this model is evaluated using multiple n-gram matching strategies:
* **BLEU (Bilingual Evaluation Understudy):** Configured to evaluate corpus-level precision using filtered token arrays to prevent special-token (e.g., `START`, `END`) biases. 
* **ROUGE (Recall-Oriented Understudy for Gisting Evaluation):** Used to measure recall and structural similarity against the ground-truth Hindi translation
