# Car Plate Recognition
This is a program to detect the car plate and recognize every character on it.

## Hardware required
1. Jetson Nano
2. Logitech C270 HD Webcam

## Dataset Preparation
Collect the image dataset of car plate and anotate every car plate in the image. You can use [Roboflow](https://roboflow.com/) to do anotation process.

## Model creation
You can use my model directly or create your own model using [ModelCreation.ipynb.](https://github.com/ibnuazman/CarPlateRecognition/blob/main/ModelCreation.ipynb)

## Jetson Nano configuration
It is very important to configure your Jetson Nano first before run the program. Install all required library needed to run this program smoothly.

### Create an environment
Create a new environment using Python verion 3.8 (if you do not created it yet)
```
conda create -n myenv python=3.8
```
You can manage your environment [here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#viewing-a-list-of-your-environments)

### Installation
1. Clone the YOLOv5 repo
```
git clone https://github.com/ultralytics/yolov5
cd yolov5
```
2. Modify requirements.txt and download it
- Locate and open YOLOv5 directory
- Open requirements.txt using text editor
- Comment #torch>=1.7.0 #torchvision>=0.8.
```
pip3 install -r requirements.txt
```
3. Install EasyOCR\n
EasyOCR is used to convert the character in the image to text
```
pip3 install easyocr
```
4. Install Pytorch
```
git clone --recursive --branch 1.7 http://github.com/pytorch/pytorch
cd pytorch
python3.8 -m pip install -r requirements.txt
python3.8 setup.py install
```
5. Install torchvision
```
cd ~
git clone --branch v0.8.1 https://github.com/pytorch/vision torchvision
cd torchvision
export BUILD_VERSION=0.8.1
python3 setup.py install --user
```
6. Check GPU details
Check if you can GPU or not. Also check the version of Pytorch and torchvision to verify the installation is completed.
```
cd ~
python3 -c "import torchvision; print('CUDA available: ' + str(torch.cuda.is_available()))"
python3 -c "import torch; print(torch.__version__)"
python3 -c "import torchvision; print(torchvision.__version__)"
```
***If you face some problems with libavformat and libswcale, run this code***
```
sudo apt-get install libavformat-dev
sudo apt-get install libswscale-dev
```
7. OpenCV Configuration
```
pip3 uninstall opencv-python-headless -y
pip install opencv-python --upgrade
```

### Run the inference program
```
python3 main.py
```

## Conclusion
Thank you to all that helped me through this program. Thanks to my friends, lecturers and family for supporting me. Thanks to all of you for running my program. Please let me know if you have any problems during running the program. You can reach me at my [email](ibnuazman.11@gmail.com)
