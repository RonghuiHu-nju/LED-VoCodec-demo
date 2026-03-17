# LED: Latent Enhancement Distillation for Joint Audio Codec and Speech Enhancement

[![Audio Samples](https://img.shields.io/badge/🎧_Listen_to-Audio_Demo-blue?style=for-the-badge)](https://你的GitHub用户名.github.io/你的仓库名/)
[![Paper](https://img.shields.io/badge/📄_Read-Paper-green?style=for-the-badge)](#) 

[cite_start]This repository contains the official audio demonstrations for our paper **"Latent Enhancement Distillation for Joint Audio Codec and Speech Enhancement"**[cite: 1, 2]. 

[cite_start]🏆 **Our LED-VoCodec system ranked 1st in the 2025 Low-Resource Audio Codec (LRAC) Challenge**[cite: 48].

## 🌐 Interactive Audio Demo
Please visit our **[GitHub Pages Audio Demo](https://你的GitHub用户名.github.io/你的仓库名/)** to listen to the reconstructed speech samples across different bitrates (1 kbps and 6 kbps) under noisy and reverberant conditions.

## 📖 Abstract
[cite_start]Neural audio codecs (NACs) have recently emerged as a powerful paradigm for low-bitrate speech compression[cite: 5, 16, 17]. [cite_start]Their widespread deployment on resource-constrained edge devices imposes strict requirements on computational complexity and bitrate[cite: 6]. [cite_start]Meanwhile, real-world environments often contain noise, reverberation, and other distortions that degrade speech quality, making robust speech coding under such conditions a persistent challenge[cite: 7]. 

[cite_start]In this work, we propose **Latent Enhancement Distillation (LED)**, a codec-agnostic training paradigm for joint audio coding and speech enhancement (SE)[cite: 8]. [cite_start]Through cross-task knowledge distillation (CKD) in the latent space, LED adopts a three-stage progressive training scheme that enables a single NAC framework to perform effective denoising and dereverberation while preserving high-fidelity coding[cite: 9].

## ⚙️ The LED Paradigm

![LED Paradigm Schematic](assets/figure1_led_paradigm.png)
*Figure: The Schematic of the LED paradigm. The framework involves three progressive stages: (1) training a high-fidelity teacher on clean speech, (2) distilling the student encoder via cross-task knowledge distillation, and (3) fine-tuning the student decoder.*
