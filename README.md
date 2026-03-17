# Latent Enhancement Distillation (LED) for Joint Audio Codec and Speech Enhancement

[![Status](https://img.shields.io/badge/Status-Under_Review_(TASLP)-blue)](#)
[![Challenge](https://img.shields.io/badge/LRAC_Challenge_2025-1st_Place-gold)](#)

This repository contains the official audio demonstrations for our paper **"Latent Enhancement Distillation for Joint Audio Codec and Speech Enhancement"** (currently under review for IEEE/ACM TASLP). 

🏆 **Our proposed LED-VoCodec system ranked 1st in the 2025 Low-Resource Audio Codec (LRAC) Challenge.**

## 📖 Abstract
Neural audio codecs (NACs) have recently emerged as a powerful paradigm for low-bitrate speech compression. Their widespread deployment on resource-constrained edge devices imposes strict requirements on computational complexity and bitrate. Meanwhile, real-world environments often contain noise, reverberation, and other distortions that degrade speech quality, making robust speech coding under such conditions a persistent challenge. 

In this work, we propose **Latent Enhancement Distillation (LED)**, a codec-agnostic training paradigm for joint audio coding and speech enhancement (SE). Through cross-task knowledge distillation (CKD) in the latent space, LED adopts a three-stage progressive training scheme that enables a single NAC framework to perform effective denoising and dereverberation while preserving high-fidelity coding. 

---
## 🎧 Audio Samples

> **Instructions:** Click on the **[🔊 Listen]** links below. It will securely open GitHub's native audio player for that specific file.

### 1. Reference & Degraded Inputs
| Condition | Sample 1 (`fileid_1`) | Sample 2 (`fileid_2`) |
| :--- | :---: | :---: |
| **Clean (Reference)** | [🔊 Listen to Clean](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_clean.wav) | [🔊 Listen to Clean](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_clean.wav) |
| **Raw (Noisy/Reverb)** | [🔊 Listen to Raw](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_raw.wav) | [🔊 Listen to Raw](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_raw.wav) |

### 2. High Bitrate Comparisons (approx. 6 kbps)
| Model | Bitrate | Sample 1 (`fileid_1`) | Sample 2 (`fileid_2`) |
| :--- | :---: | :---: | :---: |
| **LED-VoCodec (Ours)** | 6 kbps | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_LED-VoCodec-6kbps.wav) | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_LED-VoCodec-6kbps.wav) |
| **LED-VoCodec-L (Ours)** | 6 kbps | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_LED-VoCodec-L-6kbps.wav) | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_LED-VoCodec-L-6kbps.wav) |
| E2E-VoCodec (Baseline) | 6 kbps | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_E2E-VoCodec-6kbps.wav) | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_E2E-VoCodec-6kbps.wav) |
| DAC (Baseline) | 6 kbps | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_DAC-6kbps.wav) | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_DAC-6kbps.wav) |
| Encodec (Baseline) | 6 kbps | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_Encodec-6kbps.wav) | [🔊 Listen to 6kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_Encodec-6kbps.wav) |

### 3. Low Bitrate Comparisons (1 kbps ~ 3 kbps)
| Model | Bitrate | Sample 1 (`fileid_1`) | Sample 2 (`fileid_2`) |
| :--- | :---: | :---: | :---: |
| **LED-VoCodec (Ours)** | 1 kbps | [🔊 Listen to 1kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_LED-VoCodec-1kbps.wav) | [🔊 Listen to 1kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_LED-VoCodec-1kbps.wav) |
| **LED-VoCodec-L (Ours)** | 1 kbps | [🔊 Listen to 1kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_LED-VoCodec-L-1kbps.wav) | [🔊 Listen to 1kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_LED-VoCodec-L-1kbps.wav) |
| E2E-VoCodec (Baseline) | 1 kbps | [🔊 Listen to 1kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_E2E-VoCodec-1kbps.wav) | [🔊 Listen to 1kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_E2E-VoCodec-1kbps.wav) |
| DAC (Baseline) | 1.5 kbps | [🔊 Listen to 1.5kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_DAC-1.5kbps.wav) | [🔊 Listen to 1.5kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_DAC-1.5kbps.wav) |
| Encodec (Baseline) | 3 kbps | [🔊 Listen to 3kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_1_Encodec-3kbps.wav) | [🔊 Listen to 3kbps](https://github.com/RonghuiHu-nju/LED-VoCodec-demo/blob/main/audio_sample/fileid_2_Encodec-3kbps.wav) |
