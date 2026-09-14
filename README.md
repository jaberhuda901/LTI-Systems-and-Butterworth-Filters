# SYSC 3501 Lab 2: Time and Frequency Responses of LTI Systems & Butterworth Filters

## 📌 Overview

This repository contains the models, data, and analysis for Laboratory 2 of the **SYSC 3501 Communication Theory** course at Carleton University. The primary goal of this project is to explore and analyze how Linear Time-Invariant (LTI) systems—specifically low-pass Butterworth filters—affect signals with varying frequency contents.

By utilizing **MATLAB** and **Simulink**, this project bridges theoretical signal processing concepts with practical simulation, demonstrating how signals transform in both the time and frequency domains.

## 🎯 Learning Objectives & Skills Acquired

* **LTI System Analysis:** Characterizing systems using their frequency response $H(f)$ and understanding signal convolution.

* **Filter Design & Behavior:** Simulating $8^{th}$-order low-pass Butterworth filters and analyzing how varying cut-off frequencies ($f_c$) impact signal amplitude and phase.

* **Fourier Series & Transforms:** Deconstructing complex periodic waveforms (like square waves) into infinite sums of sine wave harmonics and observing how filters manipulate these individual components.

* **MATLAB & Simulink Proficiency:**

  * Building block-oriented models using Simulink and the DSP Blockset.

  * Using Signal Generators, Scopes, Zero-Order Holds, and Spectrum Analyzers.

  * Writing MATLAB scripts to plot theoretical frequency responses (Bode plots).

## 🔬 Project Breakdown & Methodology

### Part 1: Filtering a Sinusoidal Signal (Time-Domain Analysis)

In this section, a pure $1\text{ Hz}$ sine wave was passed through simulated Butterworth filters with varying cut-off frequencies ($100\text{ Hz}$, $2\text{ Hz}$, and $1\text{ Hz}$).

* **Observations:**

  * When the cut-off frequency ($100\text{ Hz}$) was much higher than the signal frequency, the signal passed unattenuated with $0$ phase shift.

  * As the cut-off frequency approached the input frequency ($2\text{ Hz}$), slight phase shifts ($\approx 0.3^{\circ}$) began to appear, though amplitude remained largely intact.

  * When the cut-off matched the input frequency ($1\text{ Hz}$), the signal experienced significant attenuation (amplitude dropped to $\approx 0.706$) and a severe phase shift.

* **Frequency Response Mapping:** By locking the filter at a $4\text{ Hz}$ cut-off and sweeping the input sine wave from $1\text{ Hz}$ to $10\text{ Hz}$, an experimental amplitude vs. frequency graph was plotted. The data perfectly mirrored the theoretical exponential drop-off of an $8^{th}$-order Butterworth filter.

### Part 2: Filtering a Square Wave (Frequency-Domain Analysis)

A $1\text{ Hz}$ square wave was used to demonstrate Fourier Series principles. A square wave is theoretically composed of a fundamental frequency and infinite odd harmonics ($3\text{ Hz}, 5\text{ Hz}, 7\text{ Hz}$, etc.).

* **Observations:**

  * Passing the square wave through a $100\text{ Hz}$ filter left it largely unchanged, as most significant harmonics passed through the filter.

  * As the filter's cut-off was reduced to $4\text{ Hz}$, $2\text{ Hz}$, and finally $1\text{ Hz}$, the higher-order harmonics were stripped away.

  * Visually, the square wave became smoother and smoother, eventually resembling a pure, attenuated sine wave at the $1\text{ Hz}$ cut-off, perfectly demonstrating how low-pass filters block high-frequency transient edges.

* **Spectrum Analysis:** Using a Zero-Order Hold and a Simulink Spectrum Analyzer, the discrete frequency spikes of the harmonics were measured. The experimental decibel (dB) differences between harmonics aligned closely with the theoretical Fourier coefficients ($\vert{}C_n\vert{} = \frac{4A}{n\pi}$).

## 📊 Key Findings

The experimental data collected from the Simulink Scopes and Spectrum Analyzers successfully validated theoretical mathematical models:

1. **Amplitude Spectrum:** The experimental values for the amplitude spectrum of the input square wave closely matched the theoretical Fourier expansion values (e.g., experimental difference of $-16.82\text{ dB}$ vs theoretical $-16.34\text{ dB}$).

2. **Transfer Function** $\vert{}Y(f)\vert{} = \vert{}H(f)\vert{}\vert{}X(f)\vert{}$**:** The relationship between the input spectra, the filter's frequency response, and the output spectra was verified quantitatively, confirming the foundational equation of LTI systems.

## 🛠️ Tools Used

* **MATLAB** (Scripting, theoretical array calculations, and plotting)

* **Simulink** (System block modeling, continuous-time simulation)

* **Simulink DSP Blockset** (Analog Filter Design, Spectrum Analyzers)

## 📂 Repository Contents

* `lab2_report.pdf` - The full detailed lab report including all theoretical calculations, tables and Simulink oscilloscope screenshots.

*This repository represents coursework completed by Jaber-ul Huda for SYSC 3501.*