# *Leffa*: Learning Flow Fields in Attention for Controllable Person Image Generation

*[Leffa](https://en.wiktionary.org/wiki/leffa)* is a unified framework for controllable person image generation that enables precise manipulation of both appearance (i.e., virtual try-on) and pose (i.e., pose transfer).

<div align="center">
  <img src="https://huggingface.co/franciszzj/Leffa/resolve/main/assets/teaser.png" width="100%" height="100%"/>
</div>

## Abstract
Controllable person image generation aims to generate a person image conditioned on reference images, allowing precise control over the person’s appearance or pose. However, prior methods often distort fine-grained textural details from the reference image, despite achieving high overall image quality. We attribute these distortions to inadequate attention to corresponding regions in the reference image. To address this, we thereby propose **le**arning **f**low **f**ields in **a**ttention (***Leffa***), which explicitly guides the target query to attend to the correct reference key in the attention layer during training. Specifically, it is realized via a regularization loss on top of the attention map within a diffusion-based baseline. Our extensive experiments show that *Leffa* achieves state-of-the-art performance in controlling appearance (virtual try-on) and pose (pose transfer), significantly reducing fine-grained detail distortion while maintaining high image quality. Additionally, we show that our loss is model-agnostic and can be used to improve the performance of other diffusion models.

## Method
An overview of our *Leffa* training pipeline for controllable person image generation. The left is our diffusion-based baseline; the right is our *Leffa* loss. Note that Isrc and Itgt are the same image during training.

<div align="center">
  <img src="https://huggingface.co/franciszzj/Leffa/resolve/main/assets/leffa.png" width="100%" height="100%"/>
</div>

## Visualization
Qualitative visual results comparison with other methods. The input person image for the pose transfer is generated using our method in the virtual try-on. The visualization results demonstrate that our method not only generates high-quality images but also greatly reduces the distortion of fine-grained details.

<div align="center">
  <img src="https://huggingface.co/franciszzj/Leffa/resolve/main/assets/vis_result.png" width="100%" height="100%"/>
</div>

## Installation
Create a conda environment and install requirements:
```shell
conda create -n leffa python==3.10
conda activate leffa
cd Leffa
pip install -r requirements.txt
```

## Gradio App
Run locally:
```shell
python app.py
```

## Evaluation
We use this [code](https://github.com/franciszzj/VtonEval) for metric evaluation.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=franciszzj/Leffa&type=Date)](https://star-history.com/#franciszzj/Leffa&Date)

## Acknowledgement
Our code is based on [Diffusers](https://github.com/huggingface/diffusers) and [Transformers](https://github.com/huggingface/transformers).
We use [SCHP](https://github.com/GoGoDuck912/Self-Correction-Human-Parsing/tree/master) and [DensePose](https://github.com/facebookresearch/DensePose) to generate masks and densepose in our [Demo](https://huggingface.co/spaces/franciszzj/Leffa).
We also referred to the code of [IDM-VTON](https://github.com/yisol/IDM-VTON) and [CatVTON](https://github.com/Zheng-Chong/CatVTON).

## Citation
If you find our work helpful or inspiring, please feel free to cite it.
```
@article{zhou2024learning,
  title={Learning Flow Fields in Attention for Controllable Person Image Generation}, 
  author={Zhou, Zijian and Liu, Shikun and Han, Xiao and Liu, Haozhe and Ng, Kam Woh and Xie, Tian and Cong, Yuren and Li, Hang and Xu, Mengmeng and Pérez-Rúa, Juan-Manuel and Patel, Aditya and Xiang, Tao and Shi, Miaojing and He, Sen},
  journal={arXiv preprint arXiv:2412.08486},
  year={2024},
}
```
