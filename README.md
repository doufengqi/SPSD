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