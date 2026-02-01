# \# Machine Learning in Interpolation and Extrapolation for Nanophotonic Inverse Design

This repository contains the conceptual framework and methodology for the research paper: "Machine Learning in Interpolation and Extrapolation for Nanophotonic Inverse Design," published in ACS Omega.


# \# Overview

Inverse design in nanophotonics often relies on computationally intensive iterative solvers (e.g., adjoint optimization). This project explores the use of Artificial Neural Networks (ANNs) as high-speed surrogates. A central contribution of this work is the rigorous evaluation of how different ML architectures perform when interpolating (predicting within the training distribution) versus extrapolating (predicting for structures or spectra unseen during training).

# \# Project Objectives

\- Benchmark Architectures: Compare Deep Neural Networks (DNN), Convolutional Neural Networks (CNN), and hybrid PCA-DNN models for forward and inverse design.

\- Interpolation vs. Extrapolation: Quantify the "generalization gap" when models are tasked with designing structures for spectral responses outside the training range.

\- Transfer Learning: Evaluate the efficacy of pre-trained models (e.g., ResNet50) in predicting electromagnetic responses.
 
# \# Methodology

1\. Data Generation

 \- Physics Engine: Open-source Finite-Difference Time-Domain (FDTD) simulations (Meep).
 
 \- Dataset: 10,000 unique 2D absorbing silicon nanostructures.
 
 \- Representation: $40 \\times 40$ binary matrices (presence/absence of silicon), smoothed to represent realistic fabrication.
 

 2\. ML Architectures Evaluated
 
 \- ResNet50: Pre-trained on ImageNet and fine-tuned for optical spectra.
 
 \- Standard DNN: Fully connected layers for both forward and inverse mappings.
 
 \- CNN: Utilizing spatial correlations in the $40 \\times 40$ grid.
 
 \- Hybrid PCA+DNN: Dimensionality reduction via Principal Component Analysis (PCA) combined with a DNN.
 
 \- Tandem Networks: Forward-Inverse coupled architecture to solve the one-to-many mapping problem.

 <p align="center">
  <img src="docs/figures/Schematic representation of forward networks.pdf" width="750" alt="ML Architecture">
  <br>
  <em>Figure 1: Schematic representation of forward networks.</em>
</p>

# \# Key Results

 \- DNN Superiority in Extrapolation: While CNNs and ResNet50 excel at interpolation, standard DNNs demonstrate significantly better stability and lower error when extrapolating to unseen geometric regimes.
 
 \- Hybrid Success: Combining ANNs with classical ML (PCA) can improve training speed and interpolation accuracy, but often limits extrapolative reach.
 
 \- Generative Capability: The inverse models successfully generated structures with target spectral responses that were significantly outside the training data bounds.
 
 \- Computational Efficiency: Predictions are obtained at orders of magnitude lower time per result compared to full-wave simulations.

# \# Tech Stack

\- Programming: Python

\- ML Frameworks: TensorFlow / Keras, Scikit-learn

\- Electromagnetic Simulation: Meep (FDTD)

\- Data Handling: NumPy, Pandas, Matplotlib

# \# Citation

If you find this work useful for your research, please cite:

@article{Acharige2022,
  author = {Acharige, Didulani and Johlin, Eric},
  title = {Machine Learning in Interpolation and Extrapolation for Nanophotonic Inverse Design},
  journal = {ACS Omega},
  volume = {7},
  number = {37},
  pages = {33537-33547},
  year = {2022},
  doi = {10.1021/acsomega.2c04526},
  publisher = {American Chemical Society}
}



# \# Code \& Data Access

The code in this repository provides the logic for the model architectures and evaluation metrics.
 \- Dataset: The full simulation dataset is available upon reasonable request.
 
 \- Usage: Please contact the author for specific implementation details for commercial or collaborative research.

# \# Contact

  \- Didulani Acharige 
  
  \- Department of Mechanical and Materials Engineering, Western University
  
  \- Email : dsalwath@uwo.ca


