# GB-RVFL-classifier
 The Granular Ball Random Vector Functional Link (GB-RVFL) model is an advanced adaptation of the Random Vector Functional Link (RVFL) network, designed to address key limitations in the original RVFL architecture while enhancing its performance and applicability. Below is an explanation of the GB-RVFL model and how it improves over RVFL:
I have use the GBRVFL for the classification of the EEG dataset using ASU and KaraOne dataset .
ABOUT Dataset:
The KaraOne and ASU datasets are prominent datasets used in imagined speech classification and EEG signal processing research. Here's a concise overview of both datasets, their acquisition process, preprocessing, and data partitioning:

KaraOne Dataset
Source: University of Toronto
Participants:

12 participants (8 males, 4 females, age 27.4 ± 5 years).
All were right-handed, fluent in North American English (10 native speakers, 2 fluent since age 6).
No history of neurological disorders, drug misuse, or sensory/motor impairments.
Data Acquisition:

EEG Equipment: Neuroscan Quick-cap with 64 channels, following the 10–20 international standard.
Amplifier: SynAmps RT amplifier.
Sampling Rate: 1 kHz.
Tasks: Imagined and articulated speech.
4 words: pat, pot, knew, gnaw.
7 phonemic/syllabic prompts: /iy/, /uw/, /piy/, /tiy/, /diy/, /m/, /n/.
Each prompt was presented 12 times.
Visual cues were shown to participants seated in chairs.
Preprocessing:

Ocular Artifact Removal: Weighted Independent Component Analysis (WICA) using EEGLAB's fastICA.
Filtering:
Band-pass filter: 1–50 Hz.
Small Laplacian filter for spatial smoothing using neighboring channels.
Normalization: Channel-wise mean subtraction.
ASU Dataset
Source: Human Oriented Robotics and Controls (HORC) Lab, Arizona State University.

Participants:

15 participants (11 males, 4 females, age 22–32).
Each performed 1–3 sessions of imagined speech tasks, with 100 trials per word.
Data Acquisition:

EEG Equipment: Brain Products ActiCHamp amplifier system with 64 electrodes (10–20 International System).
Sampling Rate: Initially 1 kHz, downsampled to 256 Hz.
Tasks:
Short Words: in, out, up.
Long Words: cooperate, independent.
Vowels: /a/, /i/, /u/.
Stimuli were presented randomly on a monitor.
Preprocessing:

Filtering:
Band-pass filter: 8–70 Hz to remove low-frequency and EMG artifacts.
Notch filter at 60 Hz for line noise.
Adaptive filters for ocular artifacts.
Data Partitioning
KaraOne Dataset:
Split into 80% training/validation and 20% testing using a MATLAB script.
ASU Dataset:
Preprocessed .mat files with task labels were used.
More about the Model:
Granular Ball Random Vector Functional Link (GB-RVFL) Network
The GB-RVFL network is a scalable and robust extension of the standard Random Vector Functional Link (RVFL) network, achieved by integrating Granular Ball (GB) computing with RVFL principles. Below, we outline its core formulation and characteristics.

Key Concepts
Granular Ball (GB):
A GB represents a subset of the data encapsulating its center and associated label. GBs are coarser representations of the data, reducing complexity while preserving essential patterns.

Core Matrices:

Matrix of Centers (
𝐶
C): Contains the centers of the GBs derived from the training dataset.
Class Matrix (
𝑌
Y): Represents the labels/classes of the GBs.
Advantages of GB-RVFL
Robustness:

Why?
GB-RVFL leverages the coarse granularity of GBs, focusing on the central distribution of data. Noise and outliers, typically located farther from the centers, exert minimal influence on the model.
How?
GB-RVFL trains on GBs instead of individual data points.
It prioritizes information around the centers, capturing the most significant features of the sample space.
Result: Enhanced resilience to noisy data and outliers.
Scalability:

Why?
GBs significantly reduce the number of data points needed for training.
How?
Instead of inverting large matrices based on all training samples, GB-RVFL uses the GB center matrix, which is much smaller.
Result: Reduced computational complexity, enabling scalability for large datasets.
Formulation![GBRVFL](https://github.com/user-attachments/assets/4da79a77-59dc-4ca7-9cd7-83b65fc7a84e)

Granular Ball Representation:


Robustness & Scalability Validation
Robustness:

Section 4.5 compares GB-RVFL's performance against baseline models on noisy datasets, demonstrating superior noise tolerance.
Scalability:

Section 4.6 provides experimental evidence of the model's efficiency on large datasets, supported by complexity analysis in Section 3.3.
Conclusion
GB-RVFL transforms the standard RVFL by introducing granular-level computation. It reduces the data representation size while enhancing model robustness and scalability, making it ideal for real-world applications with noisy or large-scale datasets.

the FLOW chart for the GB-RVFL:
![GB-RVFL flow chat](https://github.com/user-attachments/assets/724cd446-1f77-4be1-a2c8-f3ed41acb915)
