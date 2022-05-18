# TEXT2FACE-SUPER_RESOLUTION
ECE - GY 7123 DEEP LEARNING


N - DCGAN / N - SAGAN / N - DFGAN

Install the libraries using !pip install requirements.txt

sentence-transformers==1.1.0
wandb==0.10.27

Run the Python Notebooks


Image Super Resolution Command :

//Helen Dataset
python test.py --gpus 1 --model sparnet --name SPARNet_S16_V4_Attn2D --load_size 128 --dataset_name single --dataroot test_dirs/Helen_test_DIC/LR --pretrain_model_path ./pretrain_models/SPARNet-V16-S4-epoch20.pth --save_as_dir results_helen/SPARNet_S16_V4_Attn2D/

//CelebA Dataset
python test.py --gpus 1 --model sparnethd --name SPARNetHD_V4_Attn2D --res_depth 10 --att_name spar --Gnorm 'in' --load_size 512 --dataset_name single --dataroot test_dirs/CelebA-TestN/ --pretrain_model_path ./pretrain_models/SPARNetHD_V4_Attn2D_net_H-epoch10.pth --save_as_dir results_CelebA-TestN/SPARNetHD_V4_Attn2D/

//Find the FID value
python -m pytorch_fid results_CelebA-TestN/SPARNetHD_V4_Attn2D/ test_dirs/CelebAHQ-Test-HR 

![image](https://user-images.githubusercontent.com/16959405/168947339-0ef2e5ae-d929-4147-abba-f7fa1a83198c.png)

![image](https://user-images.githubusercontent.com/16959405/168947380-407f0ea4-4893-43ae-8321-78b288ce7dd2.png)

![image](https://user-images.githubusercontent.com/16959405/168947410-5cd96bd3-377a-4e86-90a3-cb71b695fd41.png)
