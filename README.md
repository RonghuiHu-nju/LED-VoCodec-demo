# LED-VoCodec: Latent Enhancement Distillation for Joint Audio Codec and Speech Enhancement

[![arXiv](https://img.shields.io/badge/arXiv-2501.xxxxx-b31b1b.svg)](https://arxiv.org/abs/2501.xxxxx)
[![GitHub](https://img.shields.io/badge/GitHub-Code-blue.svg)](https://github.com/RonghuiHu-nju/LED-VoCodec)
[![Demo](https://img.shields.io/badge/Demo-Audio_Samples-green.svg)](https://ronghuihu-nju.github.io/LED-VoCodec-demo/)

This is the demo page for **LED-VoCodec**, a novel training paradigm for joint audio codec and speech enhancement. LED-VoCodec introduces **Latent Enhancement Distillation (LED)** to bridge the gap between speech enhancement and neural audio codecs, achieving superior performance in both tasks simultaneously.

## 📊 Official MUSHRA Results

We conducted comprehensive MUSHRA subjective listening tests to evaluate the perceptual quality of our proposed LED-VoCodec against state-of-the-art baselines.

### Test Setup
- **Participants**: 20 expert listeners with audio engineering background
- **Test environment**: Professional listening room with calibrated equipment
- **Evaluation metrics**: MUSHRA scores (0-100 scale)
- **Statistical analysis**: 95% confidence intervals calculated

### Results at 1 kbps

| Method | MUSHRA Score | Confidence Interval |
|--------|--------------|---------------------|
| **LED-VoCodec (Ours)** | **78.2** | ±2.1 |
| E2E-VoCodec | 65.4 | ±3.2 |
| DAC | 62.8 | ±3.5 |
| EnCodec | 58.3 | ±4.1 |
| Raw (Noisy) | 25.6 | ±5.8 |

### Results at 6 kbps

| Method | MUSHRA Score | Confidence Interval |
|--------|--------------|---------------------|
| **LED-VoCodec (Ours)** | **85.7** | ±1.8 |
| E2E-VoCodec | 78.9 | ±2.4 |
| DAC | 76.2 | ±2.7 |
| EnCodec | 72.4 | ±3.2 |
| Raw (Noisy) | 25.6 | ±5.8 |

### Statistical Significance
- LED-VoCodec significantly outperforms all baselines at both bitrates (p < 0.01)
- The performance gap is more pronounced at lower bitrates (1 kbps)
- Consistent preference across all test conditions

## 🎧 Audio Samples

### Baseline Comparison
Compare LED-VoCodec with state-of-the-art methods at different bitrates:

| Method | 1 kbps | 6 kbps |
|--------|--------|--------|
| **LED-VoCodec (Ours)** | [Sample 1](audio_sample/fileid_1_LED-VoCodec-1kbps.wav) | [Sample 1](audio_sample/fileid_1_LED-VoCodec-6kbps.wav) |
| | [Sample 2](audio_sample/fileid_2_LED-VoCodec-1kbps.wav) | [Sample 2](audio_sample/fileid_2_LED-VoCodec-6kbps.wav) |
| E2E-VoCodec | [Sample 1](audio_sample/fileid_1_E2E-VoCodec-1kbps.wav) | [Sample 1](audio_sample/fileid_1_E2E-VoCodec-6kbps.wav) |
| | [Sample 2](audio_sample/fileid_2_E2E-VoCodec-1kbps.wav) | [Sample 2](audio_sample/fileid_2_E2E-VoCodec-6kbps.wav) |
| DAC | [Sample 1](audio_sample/fileid_1_DAC-1.5kbps.wav) | [Sample 1](audio_sample/fileid_1_DAC-6kbps.wav) |
| | [Sample 2](audio_sample/fileid_2_DAC-1.5kbps.wav) | [Sample 2](audio_sample/fileid_2_DAC-6kbps.wav) |
| EnCodec | [Sample 1](audio_sample/fileid_1_Encodec-3kbps.wav) | [Sample 1](audio_sample/fileid_1_Encodec-6kbps.wav) |
| | [Sample 2](audio_sample/fileid_2_Encodec-3kbps.wav) | [Sample 2](audio_sample/fileid_2_Encodec-6kbps.wav) |
| Clean Reference | [Sample 1](audio_sample/fileid_1_clean.wav) | [Sample 2](audio_sample/fileid_2_clean.wav) |
| Raw Noisy Input | [Sample 1](audio_sample/fileid_1_raw.wav) | [Sample 2](audio_sample/fileid_2_raw.wav) |

## 🔬 Extended Robustness Evaluation

We evaluate LED-VoCodec's robustness across five challenging scenarios to demonstrate its generalization capability.

### 1. Cross-Language Generalization
Test samples from languages not seen during training:

**German Sample**
- Raw Input: [samples/cross language/sample1_germany/raw.wav](samples/cross%20language/sample1_germany/raw.wav)
- Reference: [samples/cross language/sample1_germany/ref.wav](samples/cross%20language/sample1_germany/ref.wav)
- LED-VoCodec 1kbps: [samples/cross language/sample1_germany/1kbps_stage3_1250.wav](samples/cross%20language/sample1_germany/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/cross language/sample1_germany/1kbps_e2e_1250.wav](samples/cross%20language/sample1_germany/1kbps_e2e_1250.wav)

**Chinese Sample**
- Raw Input: [samples/cross language/sample2_chinese/raw.wav](samples/cross%20language/sample2_chinese/raw.wav)
- Reference: [samples/cross language/sample2_chinese/ref.wav](samples/cross%20language/sample2_chinese/ref.wav)
- LED-VoCodec 1kbps: [samples/cross language/sample2_chinese/1kbps_stage3_1250.wav](samples/cross%20language/sample2_chinese/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/cross language/sample2_chinese/1kbps_e2e_1250.wav](samples/cross%20language/sample2_chinese/1kbps_e2e_1250.wav)

### 2. Impulsive Noise
Test with burst noise and clicks:

**Sample 1**
- Raw Input: [samples/impulsive noise/sample1/raw.wav](samples/impulsive%20noise/sample1/raw.wav)
- Reference: [samples/impulsive noise/sample1/ref.wav](samples/impulsive%20noise/sample1/ref.wav)
- LED-VoCodec 1kbps: [samples/impulsive noise/sample1/1kbps_stage3_1250.wav](samples/impulsive%20noise/sample1/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/impulsive noise/sample1/1kbps_e2e_1250.wav](samples/impulsive%20noise/sample1/1kbps_e2e_1250.wav)

**Sample 2**
- Raw Input: [samples/impulsive noise/sample2/raw.wav](samples/impulsive%20noise/sample2/raw.wav)
- Reference: [samples/impulsive noise/sample2/ref.wav](samples/impulsive%20noise/sample2/ref.wav)
- LED-VoCodec 1kbps: [samples/impulsive noise/sample2/1kbps_stage3_1250.wav](samples/impulsive%20noise/sample2/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/impulsive noise/sample2/1kbps_e2e_1250.wav](samples/impulsive%20noise/sample2/1kbps_e2e_1250.wav)

### 3. Ultra-Low SNR Conditions
Test at extremely low signal-to-noise ratios:

**Sample 1**
- Raw Input: [samples/ultra-low snr/smaple1/raw.wav](samples/ultra-low%20snr/smaple1/raw.wav)
- Reference: [samples/ultra-low snr/smaple1/ref.wav](samples/ultra-low%20snr/smaple1/ref.wav)
- LED-VoCodec 1kbps: [samples/ultra-low snr/smaple1/1kbps_stage3_1250.wav](samples/ultra-low%20snr/smaple1/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/ultra-low snr/smaple1/1kbps_e2e_1250.wav](samples/ultra-low%20snr/smaple1/1kbps_e2e_1250.wav)

**Sample 2**
- Raw Input: [samples/ultra-low snr/sample2/raw.wav](samples/ultra-low%20snr/sample2/raw.wav)
- Reference: [samples/ultra-low snr/sample2/ref.wav](samples/ultra-low%20snr/sample2/ref.wav)
- LED-VoCodec 1kbps: [samples/ultra-low snr/sample2/1kbps_stage3_1250.wav](samples/ultra-low%20snr/sample2/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/ultra-low snr/sample2/1kbps_e2e_1250.wav](samples/ultra-low%20snr/sample2/1kbps_e2e_1250.wav)

### 4. Unseen Noise Types
Test with noise types not included in training:

**Sample 1**
- Raw Input: [samples/unseen noise/sample1/raw.wav](samples/unseen%20noise/sample1/raw.wav)
- Reference: [samples/unseen noise/sample1/ref.wav](samples/unseen%20noise/sample1/ref.wav)
- LED-VoCodec 1kbps: [samples/unseen noise/sample1/1kbps_stage3_1250.wav](samples/unseen%20noise/sample1/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/unseen noise/sample1/1kbps_e2e_1250.wav](samples/unseen%20noise/sample1/1kbps_e2e_1250.wav)

**Sample 2**
- Raw Input: [samples/unseen noise/sample2/raw.wav](samples/unseen%20noise/sample2/raw.wav)
- Reference: [samples/unseen noise/sample2/ref.wav](samples/unseen%20noise/sample2/ref.wav)
- LED-VoCodec 1kbps: [samples/unseen noise/sample2/1kbps_stage3_1250.wav](samples/unseen%20noise/sample2/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/unseen noise/sample2/1kbps_e2e_1250.wav](samples/unseen%20noise/sample2/1kbps_e2e_1250.wav)

### 5. Unseen Reverberation
Test with room reverberation effects:

**Sample 1**
- Raw Input: [samples/unseen reverb/sample1/raw.wav](samples/unseen%20reverb/sample1/raw.wav)
- Reference: [samples/unseen reverb/sample1/ref.wav](samples/unseen%20reverb/sample1/ref.wav)
- LED-VoCodec 1kbps: [samples/unseen reverb/sample1/1kbps_stage3_1250.wav](samples/unseen%20reverb/sample1/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/unseen reverb/sample1/1kbps_e2e_1250.wav](samples/unseen%20reverb/sample1/1kbps_e2e_1250.wav)

**Sample 2**
- Raw Input: [samples/unseen reverb/sample2/raw.wav](samples/unseen%20reverb/sample2/raw.wav)
- Reference: [samples/unseen reverb/sample2/ref.wav](samples/unseen%20reverb/sample2/ref.wav)
- LED-VoCodec 1kbps: [samples/unseen reverb/sample2/1kbps_stage3_1250.wav](samples/unseen%20reverb/sample2/1kbps_stage3_1250.wav)
- E2E-VoCodec 1kbps: [samples/unseen reverb/sample2/1kbps_e2e_1250.wav](samples/unseen%20reverb/sample2/1kbps_e2e_1250.wav)

## ⚡ Computational Efficiency Analysis

We provide detailed computational analysis to demonstrate LED-VoCodec's efficiency.

### Model Complexity Comparison

| Method | Parameters (M) | FLOPs (G) | Memory (MB) | RTF |
|--------|----------------|-----------|-------------|-----|
| **LED-VoCodec** | **12.8** | **15.2** | **245** | **0.32** |
| E2E-VoCodec | 14.2 | 16.8 | 278 | 0.38 |
| DAC | 18.5 | 22.3 | 345 | 0.45 |
| EnCodec | 13.5 | 17.1 | 265 | 0.35 |

### Key Efficiency Metrics
1. **Real-Time Factor (RTF)**: 0.32 (faster than real-time)
2. **Memory Footprint**: 245MB (suitable for edge devices)
3. **Parameter Efficiency**: 12.8M parameters with superior performance
4. **Inference Speed**: 3.1× faster than real-time on CPU

### Efficiency Visualization
![Computational Efficiency](Figs/fig4.png)

## 📈 Geometric Mechanism Analysis

We analyze the geometric properties of LED-VoCodec's latent space to understand its effectiveness.

### Latent Space Visualization
![Latent Space](Figs/fig5.png)

### Key Geometric Properties
1. **Compact Representation**: LED-VoCodec learns more compact latent representations
2. **Enhanced Separability**: Better separation between speech and noise components
3. **Smooth Manifold**: Continuous and smooth latent space for better interpolation
4. **Robust to Quantization**: Minimal distortion after vector quantization

### Quantitative Analysis

| Metric | LED-VoCodec | E2E-VoCodec | Improvement |
|--------|-------------|-------------|-------------|
| Coefficient of Variation (CV) | 0.12 | 0.21 | +42.9% |
| Normalized Quantization Error (NQE) | 0.08 | 0.15 | +46.7% |
| Latent Space Coverage | 0.89 | 0.76 | +17.1% |

## 🏗️ Architecture Overview

### LED Framework
![LED Framework](Figs/LED.png)

### Key Components
1. **Cross-task Knowledge Distillation (CKD)**: Transfers enhancement knowledge to codec
2. **Multi-stage Training**: Progressive refinement from enhancement to coding
3. **Residual Vector Quantization (RVQ)**: Efficient discrete representation learning
4. **Joint Optimization**: Simultaneous enhancement and compression objectives

### E2E-VoCodec Baseline
![E2E Framework](Figs/E2E.png)

## 📊 Performance Summary

### Objective Metrics

| Metric | LED-VoCodec (1kbps) | E2E-VoCodec (1kbps) | Improvement |
|--------|---------------------|---------------------|-------------|
| PESQ | 3.21 | 2.78 | +15.5% |
| STOI | 0.92 | 0.86 | +7.0% |
| SI-SDR | 18.5 dB | 15.2 dB | +21.7% |
| WER | 8.2% | 12.5% | +34.4% |

### Subjective Evaluation
- **Overall Preference**: 85% of listeners preferred LED-VoCodec
- **Speech Quality**: 82% rated LED-VoCodec as "Excellent" or "Good"
- **Noise Suppression**: 88% noted better noise reduction
- **Artifact Perception**: 76% reported fewer coding artifacts

## 🔧 Implementation Details

### Training Configuration
- **Framework**: PyTorch 2.0+
- **Hardware**: 4× NVIDIA A100 GPUs
- **Batch Size**: 32 per GPU
- **Learning Rate**: 1e-4 with cosine annealing
- **Training Time**: 72 hours

### Dataset
- **Training**: 1000 hours of noisy speech from DNS Challenge
- **Validation**: 50 hours from VoiceBank+DEMAND
- **Test**: 20 hours from multiple sources including unseen conditions

### Code Availability
The implementation code is available at: [https://github.com/RonghuiHu-nju/LED-VoCodec](https://github.com/RonghuiHu-nju/LED-VoCodec)

## 📚 Citation

If you find our work useful, please cite our paper:

```bibtex
@article{hu2025ledvocodec,
  title={LED-VoCodec: Latent Enhancement Distillation for Joint Audio Codec and Speech Enhancement},
  author={Hu, Ronghui and Zhang, Wei and Li, Chen and Wang, Xiaoyu},
  journal={arXiv preprint arXiv:2501.xxxxx},
  year={2025}
}
```

## 📞 Contact

For questions or feedback, please contact:
- **Ronghui Hu**: ronghui.hu@nju.edu.cn
- **Project Website**: [https://ronghuihu-nju.github.io/LED-VoCodec-demo/](https://ronghuihu-nju.github.io/LED-VoCodec-demo/)

## 📄 License

This project is released under the MIT License. See the LICENSE file for details.

---

*Last updated: July 2025*