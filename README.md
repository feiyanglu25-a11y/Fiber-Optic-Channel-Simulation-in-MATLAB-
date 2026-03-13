# Fiber-Optic-Channel-Simulation-in-MATLAB
1. Project Overview

This project is a comprehensive simulation platform designed to evaluate and compare two fundamental modulation schems-- On-off Keying (OOK) and Binary Frequency Shift Keying(BFSK)--within a realistic optical fiber environment.
The design shifts from simple theoretical modeling to robust engineering simulation. Unlike basic models, this tool accounts for real-world physical impairments such as fiber dispersion and environment stress.

2. Theoretical Principles

A. Modulation Methods

On-off Keying (OOK): A form of amplitude shift keying where the presence of a pulse represents a '1' and its absence represents a '0'. It is bandwidth-efficient but highly sensitive to noise and threshold fluctuations.

Binary Frequency Shift Keying (BFSK): Data is transmitted through discrete frequency changes of a carrier wave. While it requires more bandwidth, it offers robustness against amplitude-based noise and extinction ratio issues.

B. Optical Fiber Dispersion

Dispersion causes the optical signal to broaden in time as it propagates, which is the primary cause of Bit Error Rate (BER) degradation in high-speed links.

C. Error Sources

Signal-to-Noise Ratio (SNR(Eb/No)): Represents the ratio of signal power to background noise. Low SNR causes 'bit flipping', where noise spikes are mistaken for signal pulses.

Extinction Ratio (ER): Real-world lasers can't turn off completely. A low ER means power is leaked during '0' bits, closing the 'eye diagram' and making it harder for the receiver to distinguish between high and low states.

3. Coding Modules

Transmitter: to generate a signal
Modulator: convert the electrical signal to an optical signal
Optical source: laser output
Fiber channel: to model the propagation of the wave through the fiber 
Receiver: detects the optical power and converts it to electric power
Signal Processing: filter, sample, and demodulate the received signal 
Evaluation: compare the correctness of received message, compare the two modulations and give conclusion.

4. Operational Guide

To demonstrate the system's robustness, use the following recommended settings in the GUI：


Parameter (Default),Recommended Range,Physical Description & Impact
Fiber Length (5 km),1 - 20 km,Total propagation distance. Longer fiber increases cumulative dispersion and total attenuation.

Attenuation (0.1),0.1 - 0.5 dB/km,Signal power loss per unit length. Typical standard single-mode fiber (SSM) is ~0.2 dB/km.

GVD Beta2 (-21),-25 to -15 ps²/km,Group Velocity Dispersion. The primary cause of pulse broadening and temporal walk-off.

TOD Beta3 (0.1),0.05 - 0.2 ps³/km, Third-Order Dispersion. Leads to asymmetric pulse distortion, especially critical at higher bit rates.

Gamma (1.3),1.1 - 2.5 1/W/km, Nonlinear Coefficient. Models the Kerr effect (Self-Phase Modulation) which distorts the pulse spectrum.

Bit Rate (1 Mbps),1 - 3 Mbps,Transmission speed. Higher rates decrease the bit window, making the system more sensitive to ISI.

Samples per Bit (20),16 - 32, Numerical resolution per bit. Higher values improve the accuracy of the SSFM algorithm.

Extinction Ratio (20 dB),12 - 30 dB, Power ratio between '1' and '0'. Low ER simulates laser leakage, which heavily degrades OOK integrity.

Target Eb/N0 (12 dB),5 - 20 dB,Signal-to-Noise Ratio (SNR). Represents the noise level in the environment at the receiver end.

Propagation Speed (200),1 - 500,Simulation control. Adjusts the pause duration for the live SSFM animation in the GUI.

Gamma,1.3,1.1 - 2.5 1/W/km,Nonlinear Coefficient. Models the Kerr effect (Self-Phase Modulation) which distorts the pulse spectrum.

