# Xception-MicroNet-MultiScale-CBAM 近红外 SEM 图像 EQE 预测系统

## 项目简介

本项目基于改进的 **Xception-MicroNet-MultiScale-CBAM** 深度学习模型，实现利用近红外扫描电子显微镜（Near-Infrared Scanning Electron Microscopy, NIR-SEM）图像对钙钛矿发光二极管（Perovskite Light-Emitting Diodes, PeLEDs）的外量子效率（External Quantum Efficiency, EQE）进行高精度预测。

模型采用：

* Xception-MicroNet 轻量化骨干网络
* Multi-Scale 多尺度特征提取模块
* CBAM-LIPCA 注意力增强机制
* 端到端回归预测框架

无需重新训练模型，用户仅需加载预训练权重即可完成批量图像推理、性能预测及结果可视化分析。


## 环境要求

### Python

推荐版本：

```text
Python ≥ 3.8
```

### GPU（推荐）

为获得最佳推理速度，建议使用支持 CUDA 的 NVIDIA GPU。

例如：

* NVIDIA RTX 3060
* NVIDIA RTX 4060
* NVIDIA RTX 4070
* NVIDIA RTX 4090

CPU 环境同样可运行，但推理速度会明显降低。

---

## 依赖安装

可通过以下命令一次性安装所有依赖库：

```bash
pip install torch>=1.10.0 torchvision>=0.11.0 pandas>=1.3.0 numpy>=1.21.0 matplotlib>=3.4.0 tqdm>=4.62.0 scikit-learn>=1.0.0 pillow>=8.3.0
```

或分别安装：

```bash
pip install torch
pip install torchvision
pip install pandas
pip install numpy
pip install matplotlib
pip install tqdm
pip install scikit-learn
pip install pillow
```

---

## 预训练模型下载

本项目提供已经训练完成的模型权重文件。

### 百度网盘下载

链接：

https://pan.baidu.com/s/1KTnRsP2lPBnBj8ZCsBRwrQ

提取码：

```text
yuqa
```

---

## 权重文件配置

下载完成后，请将所有 `.pth` 文件放入推理脚本中指定的权重目录。

例如：

```text
project/
│
├── inference.py
├── model_weights/
│   ├── model_fold1.pth
│   ├── model_fold2.pth
│   └── model_fold3.pth
│
└── test_images/
```

确保代码中的路径设置正确：

```python
model_weights_path = "./model_weights"
```

---

## 数据准备

将待预测的近红外 SEM 图像放入测试目录：

```text
test_images/
├── sample_001.png
├── sample_002.png
├── sample_003.png
└── ...
```

---

## 注意事项

1. 输入图像应与训练数据具有相同或相近的 SEM 成像条件；
2. 图像分辨率应保持与训练阶段一致；
3. 推理前请确认权重文件路径正确；
4. 若使用 GPU，请确保 CUDA 环境配置正确；
5. 首次运行时建议先测试少量样本验证环境配置。

---

## 联系方式

如有问题或建议，请通过论文通讯作者或项目维护者联系。

---

