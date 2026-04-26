# XX-DETR

**Official PyTorch implementation for real-time tomato leaf disease detection on edge devices.**

![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-brightgreen)
![PyTorch 1.10+](https://img.shields.io/badge/PyTorch-1.10%2B-orange)

## ⚙️ Requirements

- Python >= 3.8
- PyTorch >= 1.10
- CUDA >= 11.0
- torchvision >= 0.11

## 🔧 Installation

```bash
git clone https://github.com/zhuojiaxiong6/XX-DETR.git
cd XX-DETR

conda create -n xxdetr python=3.8 -y
conda activate xxdetr

pip install -r requirements.txt
```

## 📊 Dataset

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

To request access to the dataset, please contact the authors.

## 🚀 Usage

### Training

```bash
python train.py --config configs/xx_detr.yaml --data_path /path/to/dataset
```

### Testing

```bash
python test.py --config configs/xx_detr.yaml --checkpoint /path/to/checkpoint.pth
```

### Inference

```bash
python inference.py --image /path/to/image.jpg --checkpoint /path/to/checkpoint.pth
```

## 📦 Pre-trained Models

| Dataset | mAP50 | Download |
|---------|-------|----------|
| M-TLD   | —     | [Baidu Pan](https://pan.baidu.com/) |

## 📄 License

Released under the [MIT License](LICENSE).
