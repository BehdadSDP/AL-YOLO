# Ultralytics YOLOv5 🚀

[![PyPI - YOLOv5](https://img.shields.io/pypi/v/yolov5?logo=pypi&logoColor=white)](https://pypi.org/project/yolov5/)
[![YOLOv5 CI](https://github.com/ultralytics/yolov5/actions/workflows/ci.yml/badge.svg)](https://github.com/ultralytics/yolov5/actions/workflows/ci.yml)
[![Downloads](https://img.shields.io/pypi/dm/yolov5)](https://pypi.org/project/yolov5/)
[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL_3.0-blue.svg)](https://opensource.org/licenses/AGPL-3.0)

Ultralytics YOLOv5 for state-of-the-art object detection, instance segmentation and image classification models.

**This README provides a brief overview. For full documentation, please visit [https://docs.ultralytics.com/yolov5/](https://docs.ultralytics.com/yolov5/).**

## Table of Contents

- [Installation](#installation)
- [Quick Start Examples](#quick-start-examples)
  - [Inference with `detect.py`](#inference-with-detectpy)
  - [Training with `train.py`](#training-with-trainpy)
  - [Validation with `val.py`](#validation-with-valpy)
- [License](#license)
- [Contributing](#contributing)
- [Citation](#citation)

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/ultralytics/yolov5  # clone
cd yolov5
pip install -r requirements.txt  # install
```

Alternatively, install via pip (may lag behind the latest GitHub version):
```bash
pip install yolov5
```

## Quick Start Examples

Download pretrained weights (e.g., `yolov5s.pt` for a small, fast model) or train your own.

```bash
# Download yolov5s.pt (if not already present)
# You might need to run this from within the cloned yolov5 directory
# or provide an explicit download path if using pip install.
# Example using wget:
# wget https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5s.pt
```

### Inference with `detect.py`

Run inference on various sources like images, videos, directories, webcams, etc.

```bash
python detect.py --weights yolov5s.pt --source 0                               # webcam
                                              img.jpg                         # image
                                              vid.mp4                         # video
                                              screen                          # screenshot
                                              path/                           # directory
                                              'path/*.jpg'                    # glob
                                              'https://youtu.be/LNwODJXcvt4'  # YouTube
                                              'rtsp://example.com/media.mp4'  # RTSP, RTMP, HTTP stream
```

Results are saved to `runs/detect/exp*/`.

### Training with `train.py`

Train a YOLOv5 model on a custom dataset (e.g., `coco128.yaml`).

```bash
# Train from scratch (replace yolov5s.yaml with desired model config)
# python train.py --data coco128.yaml --weights '' --cfg yolov5s.yaml --img 640

# Train from pretrained weights (recommended)
python train.py --data coco128.yaml --weights yolov5s.pt --img 640 --epochs 100 --batch-size 16
```

Specify your dataset configuration in a `.yaml` file (see `data/coco128.yaml` for an example). Training results and weights are saved to `runs/train/exp*/`.

### Validation with `val.py`

Validate a trained YOLOv5 model on a validation dataset.

```bash
python val.py --weights yolov5s.pt --data coco128.yaml --img 640 --task test # Use task 'test' for test set or 'val' for val set
```

Validation results (metrics, plots) are saved to `runs/val/exp*/`.

## License

YOLOv5 is licensed under the **AGPL-3.0 License**. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please see the [CONTRIBUTING.md](CONTRIBUTING.md) guide for details on how to contribute to the project.

## Citation

If you use YOLOv5 in your research, please cite the project. You can use the information in the [CITATION.cff](CITATION.cff) file. 