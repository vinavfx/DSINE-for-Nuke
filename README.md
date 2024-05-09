
# DSINE for Nuke [![author](https://img.shields.io/badge/by:_Francisco_Contreras-blue?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/francisco-contreras-cuevas/)
The files from the original repository were converted to be compatible with Nuke Cattery

<p align="center">
  <img width=20% src="https://github.com/baegwangbin/DSINE/raw/main/docs/img/dsine/logo_with_outline.png">
</p>

Official implementation of the paper

> **Rethinking Inductive Biases for Surface Normal Estimation** \
> CVPR 2024 [oral] \
> <a href="https://baegwangbin.com" target="_blank">Gwangbin Bae</a> and <a href="https://www.doc.ic.ac.uk/~ajd/" target="_blank">Andrew J. Davison</a> \
> <a href="https://github.com/baegwangbin/DSINE/raw/main/paper.pdf" target="_blank">[paper.pdf]</a>
<a href="https://arxiv.org/abs/2403.00712" target="_blank">[arXiv]</a> 
<a href="https://www.youtube.com/watch?v=2y9-35c719Y&t=5s" target="_blank">[youtube]</a> 
<a href="https://baegwangbin.github.io/DSINE/" target="_blank">[project page]</a>

## Abstract

Despite the growing demand for accurate surface normal estimation models, existing methods use general-purpose dense prediction models, adopting the same inductive biases as other tasks. In this paper, we discuss the **inductive biases** needed for surface normal estimation and propose to **(1) utilize the per-pixel ray direction** and **(2) encode the relationship between neighboring surface normals by learning their relative rotation**. The proposed method can generate **crisp — yet, piecewise smooth — predictions** for challenging in-the-wild images of arbitrary resolution and aspect ratio. Compared to a recent ViT-based state-of-the-art model, our method shows a stronger generalization ability, despite being trained on an orders of magnitude smaller dataset.

<p align="center">
  <img width=100% src="https://github.com/baegwangbin/DSINE/raw/main/docs/img/fig_comparison.png">
</p>

## Installation

1. Download and unzip the latest release from here.
2. Copy the extracted Cattery folder to .nuke or your plugins path.
3. In the toolbar, choose Cattery > Update or simply restart Nuke.

## Compilie (optional)
```sh
# Linux
git clone https://github.com/vinavfx/DSINE-for-Nuke.git
cd ./DSINE-for-Nuke

conda create -n dsine python=3.9
conda activate dsine
pip install -r requirements.txt

wget https://huggingface.co/bdsqlsz/qinglong_controlnet-lllite/resolve/main/Annotators/dsine.pt
python ./dsine_nuke.py
# Convert with CatFileCreator.nk
```
1. Open nuke and create the CatFileCreator node
2. in Torchscript File put ./nuke/Cattery/DSINE/DSINE.pt
3. in Cat File put ./nuke/Cattery/DSINE/DSINE.cat
4. Use 3 input and 3 output channels (rgba.red, rgba.green, rgba.blue)
