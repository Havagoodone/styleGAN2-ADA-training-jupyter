# styleGAN2-ADA-training-jupyter
**Training custom datasets in styleGAN2-ADA on Jupyter**

* [Official StyleGAN2-ADA by NIVIDIA](https://github.com/NVlabs/stylegan2-ada)

* [Paper](https://arxiv.org/abs/2006.06676)

**Training Generative Adversarial Networks with Limited Data**

Tero Karras, Miika Aittala, Janne Hellsten, Samuli Laine, Jaakko Lehtinen, Timo Aila

* [Source](https://github.com/AarohiSingla/StyleGAN2-with-adaptive-discriminator-augmentation-ADA-) from Code With Aarohi

# Environment

* OS : windows
* Anacoda
* python 3.6
* tensorflow 1.14
* Hardware Spec : Geforce RTX 3090 x 2

# If you have these erros

* **No module "PIL"**
  
  -> install pillow (ex : conda install pillow, pip install pillow)
  
* **No module "requests"

  -> install requests
  
* In addtion, you need to install **tensorflow-gpu==1.14, py-opencv** too.
* And install **appropriate version of cudatoolkit and cudnn for your Hardware.
* You need more details, Visit **Offical Site** linked above.

# Procedure

* **Preparing Custom Dataset**

  1. All the images are square and the same size. Resize all custom images to same size using openCV.
  
  2. Code needs the dataset to be in .tfrecords format. **We first need to convert our dataset to this format.** StyleGAN2-ADA has made a script that makes this conversion easy.

* **Start to train**

  1. !python train.py --outdir ./results --snap=10 --data=custom_dataset/tfrecords_dataset --augpipe=bgcfnc --res=512

      The code is just an sample. 

      There are many other arguements for training that you can modify in train.py.
      
  2. Once you have the model file, you can generate "New Images".

* **Generate a new Image**

   1. !python generate.py --outdir=out --trunc=0.5 --seeds=600-605 --network={path_to_pkl_model_file}

      You have **your own model file(pkl_model_file)** after training, so you can generate your own image.



