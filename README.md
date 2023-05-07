# Setting Up Windows For YOLOv5 Object Detection
- If you have NVIDIA Graphics Card on your device, you can [run YOLOv5 using local GPU support](README.md#Running-YOLOv5-with-local-NVIDIA-GPU-support). If you don't have an NVIDIA Graphics Card, you need to run YOLOv5 using a CPU.
- Both of these methods will be explained further below.

## Running YOLOv5 with local NVIDIA GPU support
1. Install Anaconda
  - Click this link to download: https://www.anaconda.com/
  - After the installation is complete, go to the search box and type 'Anaconda Prompt', click on the application.
  - Run the following codes line by line to create an environment inside conda with Python v3.8 (change `GPU` to your environment name) then activate the environment.
    - `conda create -n GPU pip python=3.8`
    - `conda activate GPU`
    
2. Install cuDNN
  - NVIDIA CUDA Deep Neural Network (cuDNN) is a GPU-accelerated library of primitives for deep neural networks. It provides highly tuned implementations of routines arising frequently in DNN applications.
  - Run the following codes inside the `GPU` environment to install cuDNN:
    - `conda install -c conda-forge cudnn`

3. Install PyTorch, Torchvision, and CUDA Toolkit
  - PyTorch is a fully featured framework for building deep learning models, which is a type of machine learning that's commonly used in applications like image recognition and language processing.
  - CUDA is NVIDIA's parallel computing platform for their GPUs. Basically, it allows your machine to run parts of the computation in parallel (which is where a lot of the speed comes from).
  - Run the following codes line by line inside the `GPU` environment to download and install PyTorch, Torchvision, and CUDA Toolkit 11.8:
    - `conda install pytorch torchvision torchaudio cudatoolkit=11.8 -c pytorch -c conda-forge`
    - `conda install ipykernel`
    - `ipython kernel install --user --name=GPU`

4. Check Installation
  - To check whether PyTorch and Torchvision is installed, run the following codes line by line:
    - `python`
    - `>>> import torch`
    - `>>> print(torch.__version__)`
    - `>>> import torchvision`
    - `>>> print(torchvision.__version__)`
  - Use the following command to check CUDA installation:
    - `conda list cudatoolkit`
  - And the following command to check whether CUDA can recognize local GPU:
    - `python`
    - `>>> import torch`
    - `>>> torch.cuda.is_available()`
  - The command should return 'True' as an output if PyTorch recognize local GPU on Windows.

5. Install YOLOv5 Repository
  - Install Git inside the `GPU` environment using the following command:
    - `conda install -c anaconda git`
  - Clone the repository using the following command:
    - `git clone https://github.com/ultralytics/yolov5`
  - Locate the YOLOv5 directory at LocalDisk(C)>Users>Name>yolov5 and modify `requirements.txt`.
    - Open requirements.txt using text editor
    - Comment #torch>=1.7.0 and #torchvision>=0.8.1
    - Save the file
  - Install requirements.txt inside the `GPU` environment using the following command:
    - `conda activate GPU`
    - `cd yolov5`
    - `pip install -r requirements.txt`



# Installing YOLOv5 Repository
