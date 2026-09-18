# AI vs. Human Audio Classification using MFCC & SVM

This project focuses on identifying synthetic AI-generated audio (Text-to-Speech deepfakes) versus authentic human voice signals. Using a **Support Vector Machine (SVM)** classifier paired with **Mel-Frequency Cepstral Coefficients (MFCC)** for acoustic feature extraction, the model analyzes spectral patterns and vocal tract characteristics to detect digital audio manipulation.

📄 **[Read the Full Technical Report (PDF)](./docs/DSP_Laporan_Akhir.pdf)**

## Key Results
* **Training Accuracy:** **97.76%** overall across dataset split.
* **Testing Accuracy:** **90.77%** on unseen audio files.
* **AI Voice Recognition Accuracy:** **93.93%**.
* **Human Voice Recognition Accuracy:** **87.60%**.

## Technical Architecture & Pipeline
1. **Audio Preprocessing & Sampling:** Imports raw audio signals, normalizes amplitude, and applies pre-emphasis filtering ($1 - 0.97z^{-1}$) to sharpen high frequencies.
2. **Feature Extraction (MFCC):** Segments audio into overlapping frames (25 ms window, 10 ms hop size) using a periodic Hamming window. Extracts 13 cepstral coefficients across 26 filter banks.
3. **SVM Classification:** Trains a binary Support Vector Machine using a **Radial Basis Function (RBF) Kernel** with Z-score standardization to map non-linear decision boundaries between real and AI audio.

## System Specifications
| Parameter | Specification / Detail |
| :--- | :--- |
| **Language / Environment** | MATLAB |
| **Sampling Rate ($f_s$)** | 44,100 Hz |
| **Feature Extraction Method** | MFCC (13 Coefficients, 26 Mel Banks) |
| **Classifier Model** | Support Vector Machine (RBF Kernel, `BoxConstraint = 0.3`) |
| **Dataset Split** | 15 Training Files / 5 Testing Files (75% / 25% Split) |

## Authors & Credits
* **Binus ASO School of Engineering:** Clayvent Yuuki William, Rasyhad Aqil Wiryawan, Dwi Naya Syah Hary, Louis Oliver, Avriel Zara Xaviera[cite: 1].

> *Note: The full report, mathematical formulations, and detailed evaluation matrices are available in the [Technical Report](./docs/DSP_Laporan_Akhir.pdf).*[cite: 1]
