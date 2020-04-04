# Installation

## Extra step for NVIDIA gpu users
1. check if your gpu is supported: https://developer.nvidia.com/cuda-gpus. Only GPU compute capability 3.5 and above is supported.
2. Install Nvidia CUDA and CuDNN
- CUDA Toolkit: https://developer.nvidia.com/cuda-10.0-download-archive
  - update your GPU drivers
  - follow the installation instructions
- CuDNN: https://developer.nvidia.com/rdp/form/cudnn-download-survey
  - make an account/sign in with Google
  - take the latest CuDNN for CUDA 10.1 
  - unzip, then transfer each file in the 3 folders to the corresponding directories found in "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0"
  - the folders and files are as follows: 1. bin (cudnn64_7.dll) , 2. include (cudnn.h), 3. lib\x64 (cudnn.lib)
3. update your path (run the following if path not found in "Environment Variables")
- open command prompt, then set the path using the following commands:
  - SET PATH=C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin;%PATH%
  - SET PATH=C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\extras\CUPTI\libx64;%PATH%
  - SET PATH=C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\include;%PATH%
  - SET PATH=C:\tools\cuda\bin;%PATH%
4. restart your computer

Note: we are using CUDA v10.0 because we are using TF 2.0.x specific features. Only CUDA v10.0 is supported. 



## For all users
1. Install the latest ( Anaconda Python 3.7 ) or ( Miniconda3 Python 3.7 )
  - for anaconda: https://www.anaconda.com/distribution/#download-section
  - for miniconda for a smaller installation: https://docs.conda.io/en/latest/miniconda.html
2. unzip this Github folder in a directory of your choice (e.g. >C:\Richard\CS3244PneumoniaCNN)
3. Download data and unzip into the CS3244PneumoniaCNN folder
- Download from: https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia
4. Run "Anaconda Powershell Prompt (Anaconda3)" by searching in the windows search for "anaconda powershell"
5. cd to the CS3244PneumoniaCNN folder
6. type the following EXACTLY (even the double quotations): conda create -n "tfenv" python=3.7
- you can replace tfenv with a name of your choice. This is your conda environment to install your packages
7. update conda and pip
- run: conda update --all
- run: conda install pip
8. run: pip install -r requirements.txt
- note: for GPU users use: pip install -r requirements-gpu.txt
- note: for intel cpu users: conda install tensorflow-mkl
9. run the following
- run: conda activate tfenv
- run: jupyter notebook
10. jupyter notebook
- a browser instance should open
- click on "project.ipnyb"


Resources:  

GPU: 
- https://medium.com/analytics-vidhya/cuda-toolkit-on-windows-10-20244437e036 (outdated)
- https://www.tensorflow.org/install/gpu (for TF 2.1.x)

Anaconda:
- environment: https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html

