# TensorFlow GPU Setup

This repository provides instructions for setting up TensorFlow with GPU support using Conda on a Windows machine.

## Prerequisites

- [Anaconda](https://www.anaconda.com/download) or [Miniconda](https://docs.anaconda.com/miniconda/miniconda-install/) installed on your machine.
- [A compatible NVIDIA GPU and drivers](https://developer.nvidia.com/cuda-gpus).

## Installation Steps

### 1. Create a New Conda Environment

- First, create a new Conda environment with Python 3.10.14:
    ```bash
    conda create -n tensorGPU python==3.10.14
    ```
- Activate the new environment:
    ```bash
    conda activate tensorGPU
    ```

### 2. Install CUDA Toolkit and cuDNN

- Install the required CUDA Toolkit and cuDNN packages:
    ```bash
    conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
    ```

### 3. Install TensorFlow

- Finally, install TensorFlow with GPU support:
    ```bash
    python -m pip install "tensorflow<2.11"
    ```

## Verification
To verify that TensorFlow is using the GPU, run the following Python code:
```python
import tensorflow as tf
print("Num GPUs Available: ", len(tf.config.list_physical_devices('GPU')))
```

If TensorFlow is correctly set up, you should see the number of GPUs available.
