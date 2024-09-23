
# Van Gogh Style Transfer with ComfyUI, Stable Diffusion, and ControlNet

  

This project demonstrates how to apply Van Gogh’s style to images using ComfyUI, Stable Diffusion, ControlNet, and IPAdapter. Follow the steps below to set up the environment, install the necessary components, and run the workflow.

  

## Prerequisites

  

- Python 3.9

- CUDA installed and configured for GPU acceleration

- Ensure Python and CUDA are properly installed and available in the system PATH

  

## Getting Started

  

### Setting Up the Python Environment

  

Create a Python virtual environment using `venv` and activate it:



    # Navigate to your project directory
    
    cd  your/project/directory
    
      
    
    # Create a virtual environment
    
    python3  -m  venv  venv
    
      
    
    # Activate the virtual environment
    
    # On Windows:
    
    venv\Scripts\activate
    
    # On macOS/Linux:
    
    source  venv/bin/activate

  

## Installing ComfyUI


### 1. Clone the ComfyUI Repository and Install Necessary Dependencies


#### Clone ComfyUI

git clone https://github.com/comfyanonymous/ComfyUI.git

  

#### Navigate into the directory

cd ComfyUI

  

### 2.Install dependencies

pip install -r requirements.txt


### 3.Installing Additional Nodes Using UI Manager

To install additional nodes like ControlNet and IPAdapter, use the built-in ComfyUI Manager:

#### Start ComfyUI:

```bash
python main.py
```

Open the UI Manager by clicking the Manager button on the ComfyUI interface (as shown in the image below):

From the Manager, install the required nodes:

![ComfyUI Manager](https://github.com/muhammederem/VanGoghStyleTransfer/blob/main/assets/manager.png)


#### ComfyUI Manager

```bash
# Navigate to custom_nodes
cd ComfyUI/custom_nodes
git clone https://github.com/ltdrdata/ComfyUI-Manager.git
```

#### ControlNet

```bash
# Navigate to custom_nodes
cd ComfyUI/custom_nodes
git clone https://github.com/Fannovel16/comfyui_controlnet_aux.git
cd comfyui_controlnet_aux
pip install -r requirements.txt
```

#### IPAdapter

Create an ipadapter folder inside the models directory of ComfyUI to store IPAdapter models:
```bash
mkdir -p ComfyUI/models/ipadapter
```

### 4.Downloading and Placing Models

- **Stable Diffusion**: Download the diffusion model from this [link](https://civitai.com/models/133005?modelVersionId=357609).

  Place it in `models/checkpoints` in the ComfyUI directory.

- **ControlNet Model**: Download the ControlNet model from this [link](https://huggingface.co/stabilityai/control-lora/blob/main/control-LoRAs-rank128/control-lora-canny-rank128.safetensors).

  Place this model in `models/controlnet`.

- **IPAdapter Model**: Download the IPAdapter model from this [link](https://huggingface.co/h94/IP-Adapter/blob/main/sdxl_models/ip-adapter_sdxl_vit-h.safetensors).

  Place it in `models/ipadapter`.


### 5. Running the Workflow

After installing everything, run ComfyUI:

```bash
python main.py
```

### 6.Van Gogh Style Transfer Workflow

This project uses the following ComfyUI workflow to apply Van Gogh's style to an image:

- **Load Image**: The image to which you want to apply the Van Gogh style.
- **Load Style**: The Van Gogh style image.
- **Load Checkpoint**: Load the pre-trained model, such as Stable Diffusion checkpoint.
- **IPAdapter**: Applies a style transfer to the image.
- **Apply ControlNet**: Enhances the style transfer using ControlNet features.
- **Save Image**: Saves the final Van Gogh-styled image.

![WORKFLOW IMAGE](https://github.com/muhammederem/VanGoghStyleTransfer/blob/main/assets/workflow.png)

### 7.Troubleshooting

- **CUDA Errors**: Ensure CUDA is installed and configured correctly for GPU acceleration.
- **Model Compatibility**: ControlNet models for SD1 and SD2 are not interchangeable. Ensure you use models that match your installed Stable Diffusion version.
- **Model Paths**: Ensure all models are placed in their correct directories:
  - `models/checkpoints` for Stable Diffusion models
  - `models/controlnet` for ControlNet models
  - `models/ipadapter` for IPAdapter models
- **Image Batch Processing**: When testing style transfer with a batch of images, better results were observed with a single image rather than multiple images.




