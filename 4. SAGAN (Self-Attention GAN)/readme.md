This folder contains the implementation of SAGAN.

### 0. Introduction
- SAGAN: [Self-Attention Generative Adversarial Networks](https://arxiv.org/pdf/1805.08318.pdf)


### 1. Results
1) Qualitative Analysis

<img src = './results/samples/Face_Generation_Epoch_100.png'>

2) Quantative Analysis

| Model | IS↑ | FID↓ |
|:-----:|:-----:|:-----:|
| SAGAN | 2.094 ± 0.0174 | 6.140 |

3) Interpolation

<img src = './results/interpolation/Generated_Face_Interpolation.png'>

### 1. Dataset
Download the CelebA dataset from this [link](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html).
After downloading the dataset, please check if the directory corresponds to below:
```
+---[celeba]
|     \---[img_align_celeba]
|         +---[000001.jpg]
|         |...
|         +---[202599.jpg]
+---celeba.py
+---config.py
|   ...
+---walking in the latent space.ipynb
```

### 2. Run the Codes
1) Train
```
python train.py
```

2) Interpolation (so-called 'Walking in the latent space')

Place the pre-trained weights to `./results/weights` and run `walking in the latent space.ipynb`.

3) Generate faces (for inference)
```
python generate_faces.py
```

4) Inception Score
```
python inception_score.py
```

4) FID (Frechet Inception Distance) Score
```
python fid_score.py './celeba/img_align_celeba/' './results/inference/inference/'
```

### 3. Plot Loss
<img src = './results/plots/Face_Generation_Losses_Epoch_100.png'>
