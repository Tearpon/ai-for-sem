# Xception-MicroNet-MultiScale-CBAM 近红外 SEM 图像 EQE 预测系统

## 项目简介

本项目基于改进的 **Xception-MicroNet-MultiScale-CBAM** 深度学习模型，实现利用近红外扫描电子显微镜（Near-Infrared Scanning Electron Microscopy, NIR-SEM）图像对钙钛矿发光二极管（Perovskite Light-Emitting Diodes, PeLEDs）的外量子效率（External Quantum Efficiency, EQE）进行高精度预测。

模型采用：

* Xception-MicroNet 轻量化骨干网络
* Multi-Scale 多尺度特征提取模块
* CBAM-LIPCA 注意力增强机制
* 端到端回归预测框架

无需重新训练模型，用户仅需加载预训练权重即可完成批量图像推理、性能预测及结果可视化分析。

---

## 功能特点

### 高精度 EQE 预测

利用近红外 SEM 图像直接预测器件 EQE，无需复杂材料表征过程。

### 多尺度特征学习

融合不同尺度下的形貌信息，提高模型对晶粒结构和表面特征的感知能力。

### CBAM-LIPCA 注意力机制

自动关注与器件性能相关的重要区域，增强特征表达能力。

### 批量推理

支持批量读取 SEM 图像并自动输出预测结果。

### 自动结果可视化

自动生成：

* Prediction vs Ground Truth 散点图
* Loss 曲线
* 预测误差分析图
* 模型性能评估指标

---

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

支持常见图像格式：

```text
.png
.jpg
.jpeg
.bmp
.tif
.tiff
```

---

## 运行推理

执行：

```bash
python inference.py
```

程序将自动：

1. 加载预训练模型；
2. 读取测试图像；
3. 完成 EQE 预测；
4. 输出预测结果；
5. 保存可视化图表。

---

## 输出结果

### 预测结果表

例如：

```text
Image Name          Predicted EQE (%)
--------------------------------------
sample_001.png          17.83
sample_002.png          12.45
sample_003.png          20.17
```

同时保存：

```text
prediction_results.csv
```

---

### 可视化结果

自动生成：

```text
results/
├── prediction_scatter.png
├── error_distribution.png
├── regression_plot.png
└── metrics_report.txt
```

---

## 模型结构

```text
Input SEM Image
        │
        ▼
Xception-MicroNet Backbone
        │
        ▼
Multi-Scale Feature Fusion
        │
        ▼
CBAM-LIPCA Attention
        │
        ▼
Global Feature Aggregation
        │
        ▼
Regression Head
        │
        ▼
Predicted EQE
```

---

## 应用场景

本模型可应用于：

* 钙钛矿 LED 性能快速筛选
* 薄膜形貌-性能关联分析
* 高通量材料实验
* AI 辅助器件优化
* 智能材料表征

---

## 注意事项

1. 输入图像应与训练数据具有相同或相近的 SEM 成像条件；
2. 图像分辨率应保持与训练阶段一致；
3. 推理前请确认权重文件路径正确；
4. 若使用 GPU，请确保 CUDA 环境配置正确；
5. 首次运行时建议先测试少量样本验证环境配置。

---

## 引用

若本项目对您的研究工作有所帮助，请引用相关论文：

```bibtex
@article{XXXX,
  title={Morphology–Performance Prediction of Perovskite LEDs Using Explainable Deep Learning},
  author={XXX},
  journal={XXX},
  year={202X}
}
```

---

## 联系方式

如有问题或建议，请通过论文通讯作者或项目维护者联系。

---

**Xception-MicroNet-MultiScale-CBAM for NIR-SEM Image-Based EQE Prediction of Perovskite LEDs**
