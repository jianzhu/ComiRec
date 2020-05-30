# ComiRec

### [Arxiv](https://arxiv.org/abs/2005.09347)

Controllable Multi-Interest Framework for Recommendation.

[Yukuo Cen](https://sites.google.com/view/yukuocen), Jianwei Zhang, Xu Zou, Chang Zhou, [Hongxia Yang](https://sites.google.com/site/hystatistics/home), [Jie Tang](http://keg.cs.tsinghua.edu.cn/jietang/)

Accepted to KDD 2020 ADS Track!

## Prerequisites

- Python 3
- TensorFlow-GPU >= 1.8 (< 2.0)
- Faiss-GPU 

## Getting Started

### Installation

- Install TensorFlow-GPU 1.x

- Install Faiss-GPU based on the instructions here: https://github.com/facebookresearch/faiss/blob/master/INSTALL.md

- Clone this repo `git clone https://github.com/THUDM/ComiRec`.

### Dataset

Two datasets can be downloaded from https://www.dropbox.com/s/m41kahhhx0a5z0u/data.tar.gz?dl=0  

### Training

#### Training on the existing datasets

You can use `python src/train.py --dataset {dataset_name} --model_type {model_name}` to train a specific model on a dataset. Other hyperparameters can be found in the code. (If you share the server with others or you want to use the specific GPU(s), you may need to set `CUDA_VISIBLE_DEVICES`.) 

For example, you can use `python src/train.py --dataset book --model_type ComiRec-SA` to train ComiRec-SA model on Book dataset.

When training a ComiRec-DR model, you should set `--learning_rate 0.005`. 

#### Training on your own datasets

If you want to train models on your own dataset, you should prepare the following three(or four) files:
- train/valid/test file: Each line represents an interaction, which contains three numbers `<user_id>,<item_id>,<time_stamp>`.
- category file (optional): Each line contains two numbers `<item_id>,<cate_id>` used for computing diversity..


If you have ANY difficulties to get things working in the above steps, feel free to open an issue. You can expect a reply within 24 hours.

## Acknowledgement

The structure of our code is based on [MIMN](https://github.com/UIC-Paper/MIMN).

## Cite

Please cite our paper if you find this code useful for your research:

```
@article{cen2020controllable,
  title={Controllable Multi-Interest Framework for Recommendation},
  author={Cen, Yukuo and Zhang, Jianwei and Zou, Xu and Zhou, Chang and Yang, Hongxia and Tang, Jie},
  journal={arXiv},
  pages={arXiv--2005},
  year={2020}
}
```