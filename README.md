# TEXT2FACE-SUPER_RESOLUTION
ECE - GY 7123 DEEP LEARNING


# N - DCGAN / N - SAGAN / N - DFGAN

## Install the libraries using 

```
!pip install requirements.txt
```
The following will be installed:

- sentence-transformers==1.1.0
- wandb==0.10.27

```
!pip install requirements_facesparnet.txt
```
The following will be installed:

- torch==1.7.1
- torchvision==0.8.2
- tensorflow==2.5.0
- tensorboard==2.5.0
- tensorboardX==2.1
- opencv-python
- dlib
- scikit-image==0.17.2
- scipy==1.4.1
- pillow==7.2.0
- tqdm
- imgaug
- pytorch-fid

# Run the Python Notebooks

## Extracting the Dataset

You can download the dataset from Kaggle - https://www.kaggle.com/jessicali9530/celeba-dataset

Or from https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html

## Generator:

<img width="879" alt="image" src="https://user-images.githubusercontent.com/16959405/168954924-7bc606ba-364a-49ff-92c6-00d77fd796ab.png">

## Discriminator

<img width="854" alt="image" src="https://user-images.githubusercontent.com/16959405/168955008-8bce0098-acff-4a45-93b7-44e3aaecd5d7.png">

## Epochs

<img width="810" alt="image" src="https://user-images.githubusercontent.com/16959405/168955093-82c0065c-b3b2-4b6d-8473-e0343631473d.png">

<img width="478" alt="image" src="https://user-images.githubusercontent.com/16959405/168955139-5a26a76d-d0b4-4aa7-8ece-3f6377f3c70a.png">


Example:

Text:-

```
The male has an oval face. He sports a goatee and has sideburns. He has bushy eyebrows. The man is smiling.
```

![image](https://user-images.githubusercontent.com/16959405/168955268-91e00a8b-6306-4704-8646-ab6cb5714e9e.png)


Text:- 

```
The female has pretty high cheekbones and an oval face. Her hair is black. She has a slightly open mouth and a pointy nose. The female is smiling, looks attractive and has heavy makeup. She is wearing earrings and lipstick.
```

![image](https://user-images.githubusercontent.com/16959405/168955322-4cd077fe-cdf8-4060-9125-6c7249f8bd9e.png)


# Image Super Resolution Commands :



## Helen Dataset

```
python test.py --gpus 1 --model sparnet --name SPARNet_S16_V4_Attn2D --load_size 128 --dataset_name single --dataroot test_dirs/Helen_test_DIC/LR --pretrain_model_path ./pretrain_models/SPARNet-V16-S4-epoch20.pth --save_as_dir results_helen/SPARNet_S16_V4_Attn2D/
```

## CelebA Dataset

```
python test.py --gpus 1 --model sparnethd --name SPARNetHD_V4_Attn2D --res_depth 10 --att_name spar --Gnorm 'in' --load_size 512 --dataset_name single --dataroot test_dirs/CelebA-TestN/ --pretrain_model_path ./pretrain_models/SPARNetHD_V4_Attn2D_net_H-epoch10.pth --save_as_dir results_CelebA-TestN/SPARNetHD_V4_Attn2D/
```

## Find the FID value

```
python -m pytorch_fid results_CelebA-TestN/SPARNetHD_V4_Attn2D/ test_dirs/CelebAHQ-Test-HR 
```

![image](https://user-images.githubusercontent.com/16959405/168947339-0ef2e5ae-d929-4147-abba-f7fa1a83198c.png)

![image](https://user-images.githubusercontent.com/16959405/168947380-407f0ea4-4893-43ae-8321-78b288ce7dd2.png)

![image](https://user-images.githubusercontent.com/16959405/168947410-5cd96bd3-377a-4e86-90a3-cb71b695fd41.png)
