# Classifying Task Sub-Type States in Temporal fMRI with Temporal Higher-order Patterns

## Introduction

This project represents a pioneering effort to advance functional brain network analysis by adapting a novel machine learning model for the classification of task functional Magnetic Resonance Imaging (t-fMRI) data. Grounded in the innovative "Hypergraph Anomaly Detection in Brain" (HADiB) methodology, originally designed for unsupervised anomaly detection, this research aims to classify cognitive tasks within t-fMRI data from the Human Connectome Project (HCP). By exploring the dynamic interplay of regions of interest (ROIs) during specific tasks, such as differentiating between movements of the left or right hand, the project seeks not only to validate neuroscientific hypotheses but also to provide deeper insights into the brain's complex dynamics.

The significance of understanding brain function during specific tasks cannot be overstated. Insights gained from such understanding promise to propel neuroscientific research into new directions, potentially revolutionizing medical diagnostics and enhancing the development of Brain-Computer Interfaces. This project taps into the evolution of ML-based brain network analysis, transitioning from traditional methods to sophisticated models that incorporate the brain's network representation, temporal dynamics, and higher-order interactions.

## Project Scope

Leveraging the Human Connectome Project 1200 dataset, this project undertakes a comprehensive examination of the HADiB model, identifying its potential for t-fMRI task classification and addressing its limitations. The implementation phase, starting from scratch due to the unavailability of code, challenges and learnings, and the critical analysis of model performance form the core of this endeavor. Ethical considerations, especially the implications of deploying AI for brain scan interpretation, are meticulously addressed.

This README serves as a guide through for training the model and visualising outputs.


# Project Setup and Execution Guide

This README provides detailed instructions for setting up and executing the tFMRI Classification project. It includes information on environment setup, data retrieval, dependency installation, and how to run the project.

## Setting Up the Required Technology

To interact with the project, you'll need to run a Jupyter Notebook, which offers an interactive interface for executing code blocks and inspecting outputs. You have two main options for running a notebook:

- **Jupyter Notebook Interface:** Follow the [installation guide](https://docs.jupyter.org/en/latest/install.html#install) to set up the Jupyter Notebook Interface on your system.
- **Visual Studio Code (VSCode):** Install the "Jupyter" extension within VSCode to work with notebooks directly in the IDE.

## Getting the Data

The project requires specific data that must be downloaded and placed correctly within the project directory:

1. **If using the source code provided:** Download the dataset from [https://osf.io/s4h8j/](https://osf.io/s4h8j/). Due to its size (1.37GB), it is not included in the submission. Unzip the file and place it in the project's root directory, ensuring the path aligns with `./data/hcp/hcp_task`.
2. **GitHub repository:** A repository containing both the source code and data is available at [https://github.com/MagisV/HADiB-for-tFMRI-Classification](https://github.com/MagisV/HADiB-for-tFMRI-Classification). This method simplifies the setup process by eliminating the need to download and unzip the data and possibly the need to adjust data paths manually.

## Installing Dependencies

This project uses Python 3.9 or newer (>= 3.8). Dependency management and environment isolation are handled with `virtualenv` due to compatibility issues with TensorFlow Graph Neural Networks (`tf-gnn`) in Conda. Follow these steps:

1. Install `virtualenv` using pip:
   ```
   pip3 install virtualenv
   ```
2. Inside the project folder, create a virtual environment:
   ```
   virtualenv venv
   ```
   To specify a Python version, use:
   ```
   virtualenv -p /path/to/usr/bin/python3.9 venv
   ```
3. Activate the virtual environment:
   ```
   source venv/bin/activate
   ```
   To deactivate, use:
   ```
   deactivate
   ```
4. Install required packages from `requirements.txt`:
   ```
   pip3 install -r requirements.txt
   ```

## Running the Project

Follow these steps to execute the project successfully:

1. Adjust the data directory (`HCP_DIR`) in the code as necessary.
2. Randomness is disabled by default for reproducibility. Enable non-deterministic behaviour by commenting out the respective code block.
3. Set central parameters like tasks, `s_max`, batch size, and subject IDs in the `DataLoader`.
4. Execute all code cells up to `build_model` to train the model. Training time varies based on parameters.
5. Set window sizes, compile the model, and fit it by running the cells under "Fitting the Model".
6. Test the model's generalisability with the provided test set under "Testing".
7. Optionally, train the model with different combinations of window sizes and tasks, or use k-fold cross-validation as detailed in the project documentation.

For more information or help, refer to the project's documentation or the README file.