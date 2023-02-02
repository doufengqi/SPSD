# A SURFACE DEFECT DETECTION METHOD OF STEEL PLATE BASED ON YOLOv7

## 1. 环境配置

### 1.1. 环境配置

- python 3.8
- cuda 11.6
- cudnn 8.3.02
- pytorch(1.13.1+cu116) : pip3 install torch torchvision torchaudio
  --extra-index-url https://download.pytorch.org/whl/cu116
- pip install -r requirements.txt

```python
  # 检测pytorch cuda cudnn是否安装成功
import torch

print(torch.__version__)
print(torch.version.cuda)
print(torch.backends.cudnn.version())
print(torch.cuda.is_available())
```

### 1.2. 数据集

- 将数据集放在data文件夹下
- 数据集格式

```
- data
  -your_dataset
    -images
      -train
        -0001.jpg
        -0002.jpg
        -0003.jpg
        -...
      -val
        -0001.jpg
        -0002.jpg
        -0003.jpg
        -...
    -labels
      -train
        -0001.txt
        -0002.txt
        -0003.txt
        -...
      -val
        -0001.txt
        -0002.txt
        -0003.txt
        -...
```

## 2. 修改配置文件neu_det.yaml

### 2.1. 修改数据集路径 (绝对路径)

    train: E:\Project\YOLO\yolov7\data\neu_det\images\train  
    val: E:\Project\YOLO\yolov7\data\neu_det\images\val  
    test: E:\Project\YOLO\yolov7\data\neu_det\images\val

## 3. 训练

```
#以数据集neu 显卡3060 6G为例

python train.py
--cfg
cfg/training/yolov7_neu.yaml
--data
data/neu_det.yaml
--device
0
--batch-size
8
--workers
2
--save_period
5
--epochs
100
--weights
weights/yolov7.pt
--img-size
224
224
```