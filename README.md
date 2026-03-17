# LED-VoCodec: Latent Enhancement Distillation for Joint Audio Codec and Speech Enhancement

[![arXiv](https://img.shields.io/badge/arXiv-2503.xxxxx-b31b1b.svg)](https://arxiv.org/abs/2503.xxxxx)
[![LRAC Challenge 2025](https://img.shields.io/badge/LRAC%202025-1st%20Place-gold)](https://lrac2025.github.io/)
[![Demo](https://img.shields.io/badge/Demo-Online-blue)](https://your-demo-link.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**LED-VoCodec** is a lightweight neural audio codec that jointly performs **high-fidelity speech compression** and **robust speech enhancement** (denoising & dereverberation). It achieves state-of-the-art performance in the **2025 Low-Resource Audio Codec (LRAC) Challenge** (Track 2) and generalizes to existing codec architectures like DAC and EnCodec.

---

## ✨ Highlights

- **Unified framework** – a single model does both audio coding and enhancement.
- **Latent Enhancement Distillation (LED)** – a novel 3‑stage training paradigm that distills clean-speech representations into a student encoder via cross‑task knowledge distillation.
- **Lightweight & efficient** – as low as **3.47M parameters** and **350 MMACs/s** (LED‑VoCodec).
- **Codec‑agnostic** – can be applied to DAC, EnCodec, etc. without modifying their backbone.
- **#1 in LRAC Challenge 2025** – outperforms cascaded, end‑to‑end, and in‑network integration strategies.

---

## 🧠 Method Overview

LED trains a codec in three progressive stages:

1. **Teacher training** – a high‑fidelity codec (VoCodec) is trained on **clean speech only**.
2. **Encoder distillation** – a student encoder is trained on **degraded** (noisy + reverberant) speech to mimic the teacher’s clean-speech latent embeddings via **cross‑task knowledge distillation (CKD)**. The codebook is frozen to preserve clean‑speech statistics.
3. **Decoder fine‑tuning** – the decoder is updated (encoder & codebook frozen) using adversarial training to compensate for residual artifacts.

The resulting model inherits the teacher’s coding quality while acquiring strong enhancement capabilities.

![LED paradigm](figures/led_overview.png)  
*Figure: Three‑stage LED training (from the paper).*

---

## 🏆 Experimental Results

### LRAC Challenge 2025 (Track 2 – open test set)

| Bitrate | Model               | Params | MACs/s | Condition | PESQ ↑ | UTMOS ↑ | ESTOI (%) ↑ |
|---------|---------------------|--------|--------|-----------|--------|---------|-------------|
| 6 kbps  | LED‑VoCodec (ours)  | 3.47M  | 350M   | Noisy     | 2.16   | 3.33    | 79.14       |
|         | E2E‑VoCodec         | 3.47M  | 350M   | Noisy     | 2.07   | 3.27    | 78.32       |
|         | LED‑VoCodec‑L (ours)| 11.52M | 1.25G  | Reverb    | **2.14**| **3.62**| **64.28**   |
|         | Inn‑VoCodec         | 11.83M | 1.29G  | Reverb    | 1.43   | 3.11    | 59.07       |
| 1 kbps  | LED‑VoCodec‑L (ours)| 11.52M | 1.25G  | Clean     | **2.02**| **3.35**| **78.57**   |
|         | Teacher (clean)     | 3.47M  | 350M   | Clean     | 1.95   | 3.25    | 77.63       |

LED consistently outperforms baseline integration paradigms (E2E, cascaded, in‑network), especially under reverberation.

### Generalization to Other Codecs

LED improves **DAC** and **EnCodec** significantly without architectural changes:

- **DAC** @6 kbps: PESQ on noisy speech jumps from 1.38 → **2.57**.
- **EnCodec** @6 kbps: PESQ on noisy speech from 1.33 → **2.19**.

See the [paper](https://arxiv.org/abs/2503.xxxxx) for full tables and ablation studies.

---

## 🎧 Online Demo

Try LED‑VoCodec live in your browser:  
👉 **[Demo Website](https://your-demo-link.com)**  

Upload a noisy/reverberant speech sample and hear the enhanced, compressed output at 6 kbps or 1 kbps.

---

## ⚙️ Quick Start

### Installation

```bash
git clone https://github.com/yourname/LED-VoCodec.git
cd LED-VoCodec
pip install -r requirements.txt
