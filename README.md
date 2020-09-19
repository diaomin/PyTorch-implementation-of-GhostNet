# PyTorch-implementation-of-GhostNet
Reproduction of GhostNet as described in [GhostNet: More Features from Cheap Operations](https://arxiv.org/abs/1911.11907) on ILSVRC2012 benchmark with PyTorch framework.

# Requirements

## Dataset
Download the ImageNet dataset and move validation images to labeled subfolders. To do this, you can use the following script: https://raw.githubusercontent.com/soumith/imagenetloader.torch/master/valprep.sh

## Training recipe
* batch size 1024
* iterations 450,000
* learning rate 0.4 (on 8 gpus)
* weight decay 0.00004
* dropout rate 0.2 
* label smoothing 0.1 

# Training from scratch
Clone the repo:
```
git clone https://github.com/diaomin/PyTorch-implementation-of-GhostNet/
```
Train the model:
```
python train.py --train-dir=/path/to/train/folder/ --val-dir=/path/to/val/folder/ --model-size=1.0x
```

# Results
WIP

Performance:
| Models | MACs (M) | Params (M) | Top-1 Acc | Top-5 Acc |
|:-----------:|:-------:|:-------:|:--------:|:--------:|
| GhostNet 0.5x 224 | 2.6 |  42 | 65.5 | 86.3 |
| GhostNet 1.0x 224 | 5.2 | 141 | 72.5 | 91.0 |

Curves:
* from left to right: loss, top-1, top5
* blue for training and orange for validation
* model size of 0.5x (450,000 iters)
![training curves](https://github.com/diaomin/PyTorch-implementation-of-GhostNet/blob/master/training%20curves_0.5x.jpg)
* model size of 1.0x (300,000 iters)
![training curves](https://github.com/diaomin/PyTorch-implementation-of-GhostNet/blob/master/training%20curves_1.0x.jpg)

# To Do
* To train ghostnet with more iterations
* To train ghostnet with model size 2.0x


