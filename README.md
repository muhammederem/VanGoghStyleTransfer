# Van Gogh Style Transfer with ComfyUI, Stable Diffusion, and ControlNet

This project demonstrates how to apply Van Gogh’s style to images using ComfyUI, Stable Diffusion, ControlNet, and IPAdapter. Follow the steps below to set up the environment, install the necessary components, and run the workflow.

## Prerequisites

- Python 3.9
- CUDA installed and configured for GPU acceleration
- Ensure Python and CUDA are properly installed and available in the system PATH

## Getting Started

### 1. Setting Up the Python Environment

Create a Python virtual environment using `venv` and activate it:

```bash
# Navigate to your project directory
cd your/project/directory

# Create a virtual environment
python3 -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Installing ComfyUI

## 1. Clone the ComfyUI Repository and Install Necessary Dependencies

```bash

# Clone ComfyUI
git clone https://github.com/comfyanonymous/ComfyUI.git

# Navigate into the directory
cd ComfyUI

# Install dependencies
pip install -r requirements.txt
