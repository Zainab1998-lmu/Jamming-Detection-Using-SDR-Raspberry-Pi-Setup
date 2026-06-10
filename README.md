# Jamming-Detection-Using-SDR-Raspberry-Pi-Setup


This repository implements a Decision Tree (DT) algorithm on the processed signal features and simulates the framework described in the thesis ‘Jamming Detection and Classification using Decision Trees for Resource‑Constrained Systems’.
<h1>What Does It Do?</h1>
This system is an economical jamming detection and classification system designed to fit within the payload of the Loyola Marymount University Cube Satellite. 
The system acts as a spectrum monitor to protect spacecraft uplink communications by identifying and classifying Radio Frequency (RF) interference.  
<h1>Why This framework?</h1>
This framework uses:

1. A low-cost hardware.
2. Processesing raw signal inputs and utilizing a Decision Tree (DT) Machine Learning classifier to categorize incoming signals into four distinct classes: Clear, Single-Tone Jamming, Gaussian Jamming, or Sweep Jamming. 

The project is structured into two essential sections: the hardware setup configuration and the modular Python software pipeline. 
<h1>The Hardware Setup</h1> 

1. Raspberry Pi 4 Model B.
2. SDR ReceiverNooElec NESDR SMArt v5.
3. Receive Antenna. 
4. Signal Jammer  Source.

<h1>Operational Parameters & Environment</h1> 

- The Center Frequency: 467.57069 MHz, 
- Testing Environment:  a well-controlled lab verificationby placing the receiving antenna and the jamming/source antennas in a fixed line-of-sight configuration to eliminate environmental fading discrepancies. 

<h1>The Python Implementation</h1>
<h3>Prerequisites</h3>

- Python 3.10+
- Virtual environment (recommended)
<h3>Required Software</h3>

- Python 3.10+
- pip (Python package manager)
- Git (for cloning the repository)
<h3>Recommended Tools</h3>

- VS Code or PyCharm (for code editing)
- Terminal/Command Prompt (for running scripts)
<h3>Install Dependencies</h3>

- numpy
- pandas
- matplotlib
- pyrtlsdr
- scikit-learn

<h1>SDR connection + Incoming Signals Plotting + Traces Collection</h1>
From Trace Collection.py File: 

1. Establishes connection to the SDR client library (pyrtlsdr), applies hardware gain profiles, sets the sampling rates.
2. validates structural output via multi-domain plotting (Time, Frequency via FFT, and Spectrogram displays).
3. Automates data collection by capturing individual signal traces over short intervals, tracking the highest amplitudes across specified frequency bin regions. The system collects 500 traces per signal type across 9 distinct power variance scenarios. 
<h1>Feature Extraction</h1>
From the Feature Extraction File: 

Generateing data matrices to extract 4 explicit operational markers from each spectrum trace to build the dataset:  
1. Signal Power ($dB$)
2. Noise Floor ($dB$)
3. SNR ($dB$)
4. Edge Frequency ($Hz$)  
