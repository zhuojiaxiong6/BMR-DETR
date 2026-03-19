# DJ-DETR

**Official PyTorch implementation of "DJ-DETR: A Real-Time Tomato Leaf Disease Detection Model for Edge Device Deployment"**

![Paper](https://img.shields.io/badge/Paper-Scientific%20Reports-blue)
![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-brightgreen)
![PyTorch 1.10+](https://img.shields.io/badge/PyTorch-1.10%2B-orange)

## 📖 Introduction

Tomato foliar diseases pose a significant threat to crop yield and food safety worldwide. We propose **DJ-DETR**, an effective real-time detection system that combines Bidirectional Context Modeling and Gradient-Aware Perception for fine-grained tomato leaf disease detection.

### Key Features

- **BCPN (Bidirectional Context Pyramid Network):** Produces multi-scale lesion features through feature sequence interaction and multi-kernel depthwise convolution, effectively reducing cross-scale semantic gaps.

- **MGAT-Net (Multi-Scale Gradient-Aware Transfer Network):** Directly encodes gradient cues using Sobel operators to enhance localization stability for small or blurred lesions.

- **RFAM (Retentive Feature Aggregation Module):** Builds global dependencies while filtering background noise without sacrificing semantic coherence.

## 🏆 Performance

### Results on M-TLD Dataset

| Model | mAP | mAP50 | mAP75 | Latency |
|-------|-----|-------|-------|---------|
| DJ-DETR (Ours) | 62.98% | 78.91% | 68.52% | 54ms |

### Cross-Domain Generalization (PlantDoc)

| Model | mAP50 |
|-------|-------|
| DJ-DETR (Ours) | 48.6% |

### Edge Deployment

- **Platform:** NVIDIA Jetson Orin Nano
- **Optimization:** TensorRT FP16
- **Latency:** 54 ms (real-time capable)

## 📁 Project Structure

```
DJ-DETR/
├── README.md
├── requirements.txt
├── models/
│   ├── bcpn.py              # Bidirectional Context Pyramid Network
│   ├── mgat_net.py          # Multi-Scale Gradient-Aware Transfer Network
│   └── rfam.py              # Retentive Feature Aggregation Module
├── configs/
│   └── DJ_detr.yaml         # Configuration file
├── train.py                 # Training script
├── test.py                  # Testing script
├── inference.py             # Inference script
└── utils/
    ├── dataset.py           # Dataset loading utilities
    └── visualization.py     # Visualization tools
```

## ⚙️ Requirements

- Python >= 3.8
- PyTorch >= 1.10
- CUDA >= 11.0
- torchvision >= 0.11

## 🔧 Installation

```bash
# Clone the repository
git clone https://github.com/zhuojiaxiong6/DJ-DETR.git
cd DJ-DETR

# Create conda environment (recommended)
conda create -n djdetr python=3.8 -y
conda activate djdetr

# Install dependencies
pip install -r requirements.txt
```

## 📊 Dataset

### M-TLD Dataset

We provide a self-created tomato leaf disease dataset (M-TLD) for training and evaluation.

To obtain the dataset, please contact: 📧 zhuojx991021@163.com

### Data Format

The dataset follows the COCO format:

```
data/
├── train/
│   ├── images/
│   └── annotations.json
├── val/
│   ├── images/
│   └── annotations.json
└── test/
    ├── images/
    └── annotations.json
```

## 🚀 Usage

### Training

```bash
python train.py --config configs/DJ_detr.yaml --data_path /path/to/dataset
```

### Testing

```bash
python test.py --config configs/DJ_detr.yaml --checkpoint /path/to/checkpoint.pth
```

### Inference

```bash
python inference.py --image /path/to/image.jpg --checkpoint /path/to/checkpoint.pth
```

## 📦 Pre-trained Models

| Model | Dataset | mAP50 | Download |
|-------|---------|-------|----------|
| DJ-DETR | M-TLD | 78.91% | [Baidu Pan](https://pan.baidu.com/) |

> Baidu Pan Password: r9s9

## 📝 Citation

If you find this work useful for your research, please cite our paper:

```bibtex
@article{zhuo2025djdetr,
  title={DJ-DETR: A Real-Time Tomato Leaf Disease Detection Model for Edge Device Deployment},
  author={Zhuo, Jiaxiong and Dong, Guikun and Huang, Qingfeng and Zhou, Lei and Li, Rui and Zhao, Feixiong and Liu, Qiaoling and Yang, Xiangjun},
  journal={Scientific Reports},
  year={2025},
  publisher={Springer Nature}
}
```

## 📄 License

This project is released under the [MIT License](LICENSE).

## 🙏 Acknowledgements

This research was funded by the "Chengdu University Provincial Undergraduate Entrepreneurship Practice Project" – "Research on Fruit Recognition and Harvesting Algorithm of Citrus Harvesting Robot Based on Deep Learning" (S202511079013S) and managed by the Entrepreneurship College of Chengdu University.

## 📧 Contact

For any questions, please contact:

- **Jiaxiong Zhuo:** zhuojx991021@163.com
- **Qiaoling Liu (Corresponding Author):** liuqiaoling@cdu.edu.cn

School of Mechanical Engineering, Chengdu University, China
