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

The following tables demonstrate the reconstruction quality of the proposed LED paradigm compared to various baseline models across different bitrates. 

> **Note:** The `<audio>` players below stream directly from this repository. If they do not load immediately, please ensure your browser allows media playback on GitHub.

### 1. Reference & Degraded Inputs
| Condition | Sample 1 (`fileid_1`) | Sample 2 (`fileid_2`) |
| :--- | :---: | :---: |
| **Clean (Reference)** | <audio controls src="audio_sample/fileid_1_clean.wav"></audio> | <audio controls src="audio_sample/fileid_2_clean.wav"></audio> |
| **Raw (Noisy/Reverb)** | <audio controls src="audio_sample/fileid_1_raw.wav"></audio> | <audio controls src="audio_sample/fileid_2_raw.wav"></audio> |

### 2. High Bitrate Comparisons (approx. 6 kbps)
| Model | Bitrate | Sample 1 (`fileid_1`) | Sample 2 (`fileid_2`) |
| :--- | :---: | :---: | :---: |
| **LED-VoCodec (Ours)** | 6 kbps | <audio controls src="audio_sample/fileid_1_LED-VoCodec-6kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_LED-VoCodec-6kbps.wav"></audio> |
| **LED-VoCodec-L (Ours)** | 6 kbps | <audio controls src="audio_sample/fileid_1_LED-VoCodec-L-6kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_LED-VoCodec-L-6kbps.wav"></audio> |
| E2E-VoCodec (Baseline) | 6 kbps | <audio controls src="audio_sample/fileid_1_E2E-VoCodec-6kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_E2E-VoCodec-6kbps.wav"></audio> |
| DAC (Baseline) | 6 kbps | <audio controls src="audio_sample/fileid_1_DAC-6kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_DAC-6kbps.wav"></audio> |
| Encodec (Baseline) | 6 kbps | <audio controls src="audio_sample/fileid_1_Encodec-6kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_Encodec-6kbps.wav"></audio> |

### 3. Low Bitrate Comparisons (1 kbps ~ 3 kbps)
| Model | Bitrate | Sample 1 (`fileid_1`) | Sample 2 (`fileid_2`) |
| :--- | :---: | :---: | :---: |
| **LED-VoCodec (Ours)** | 1 kbps | <audio controls src="audio_sample/fileid_1_LED-VoCodec-1kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_LED-VoCodec-1kbps.wav"></audio> |
| **LED-VoCodec-L (Ours)** | 1 kbps | <audio controls src="audio_sample/fileid_1_LED-VoCodec-L-1kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_LED-VoCodec-L-1kbps.wav"></audio> |
| E2E-VoCodec (Baseline) | 1 kbps | <audio controls src="audio_sample/fileid_1_E2E-VoCodec-1kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_E2E-VoCodec-1kbps.wav"></audio> |
| DAC (Baseline) | 1.5 kbps | <audio controls src="audio_sample/fileid_1_DAC-1.5kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_DAC-1.5kbps.wav"></audio> |
| Encodec (Baseline) | 3 kbps | <audio controls src="audio_sample/fileid_1_Encodec-3kbps.wav"></audio> | <audio controls src="audio_sample/fileid_2_Encodec-3kbps.wav"></audio> |

---
