# How-to-install-Tensorflow-GPU
## How to install Tensorflow-GPU 1.6 on Windows

### Install Python
Download Version 3.6 64bit here: [Windows x86-64 executable installer](https://www.python.org/downloads/release/python-364/)

### Install tensorflow-gpu
````shell
cd C:\Users\<username>\AppData\Local\Programs\Python\Python36\Scripts
````
if you  tensorflow already installed so uninstalled :
````shell
pip uninstall tensorflow
````
````shell
pip install tensorflow-gpu
````

### install Nvidia Driver
Download Last Version here: [Nvidia Last Driver](http://www.nvidia.fr/Download/index.aspx?lang=fr)

### Install CUDA Tool Kit
Download Version 9 here: [CUDA Toolkit 9.0](https://developer.nvidia.com/cuda-90-download-archive?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exelocal)

### Install cuDNN
Download Version 7.0.5 here: [cuDNN v7.0.5 (Dec 5, 2017), for CUDA 9.0](https://developer.nvidia.com/rdp/cudnn-download)

unzip `cudnn-9.0-windows10-x64-v7.zip` then copy `bin` &`include` & `lib` in : 

````shell
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0
````

### Set Your Environment Variables
1. Click `Windows`+`R`  Then type `sysdm.cpl` and go to `advanced` and select `Environmental Variables`   

2. Click on the `Path` in `system variable` and select `edit`      

3. add the following paths

`C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\bin`        
`C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\libnvvp`      

### Test your Installation

```python
from tensorflow.python.client import device_lib

print(device_lib.list_local_devices())
```

#### Output: 

```python
[name: "/device:CPU:0"
device_type: "CPU"
memory_limit: 268435456
locality {
}
incarnation: 7179507163498351914
, name: "/device:GPU:0"
device_type: "GPU"
memory_limit: 2241268940
locality {
  bus_id: 1
}
incarnation: 14675117801653382741
physical_device_desc: "device: 0, name: GeForce GTX 1060 3GB, pci bus id: 0000:23:00.0, compute capability: 6.1"
```
