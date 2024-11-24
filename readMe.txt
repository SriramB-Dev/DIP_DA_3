
Image Restoration using CycleGAN and Pix2Pix  
This repository demonstrates a comparative study of two GAN based architectures— CycleGAN and Pix2Pix—to restore degraded Indian artwork images. The project involves preprocessing and training workflows specific to each architecture.  

Table of Contents  
1)Introduction
2)Requirements 
3)Dataset 
4)Workflow Overview 
5)Model Architectures
6)Training Instructions 
7)Results
 


Introduction  
Image restoration plays a vital role in preserving cultural heritage. This project applies two Generative Adversarial Network (GAN) models, Pix2Pix and CycleGAN, to restore degraded images of Indian artwork.  

Pix2Pix: A supervised GAN model requiring paired noisy and clean images for training.  
CycleGAN: An unsupervised GAN model capable of working with unpaired datasets by leveraging cycle consistency loss.  

Both approaches are evaluated using standard metrics like Peak Signal-to-Noise Ratio (PSNR) and Structural Similarity Index Measure (SSIM).  


Requirements

requirements.txt:  
The following libraries and dependencies are required:  
1)Python 3.7+  
2)TensorFlow 2.0+  
3)NumPy  
4)Matplotlib  
5)OpenCV  
6)Scikitlearn  
7)PIL  


Install all dependencies using:   
pip install r requirements.txt  
  

Dataset  
Folder Structure  
Ensure the datasets are organized as follows:  
1)Pix2Pix: combined_dataset2 folder with paired noisy and clean images.  
2)CycleGAN: image_dataset folder with unpaired noisy and clean images.  

Structure Example  

combined_dataset2/  
  /train/  
      
  /test/  
 
  /val/  
      

image_dataset/  
  

Workflow Overview  
 
Pix2Pix Workflow  
1. Preprocess the combined_dataset2 folder using gan_preprocessing.ipynb.  
2. Train the Pix2Pix model with the preprocessed dataset using pix2pix.ipynb.  

CycleGAN Workflow  
1. Directly use the image_dataset folder for unpaired image restoration.  
2. Train the CycleGAN model using dip2-2.ipynb.  



Model Architectures  

Pix2Pix  
 Generator: UNet architecture for translating noisy images to clean counterparts.  
 Discriminator: PatchGAN, ensuring authenticity at a patch level.  

CycleGAN  
 Two Generators: Mapping between noisy → clean and clean → noisy domains.  
 Two Discriminators: Evaluating the quality of generated images.  
 Cycle Consistency Loss: Ensuring reversibility between domains.  



Training Instructions  

Step-by-step Guide  

Pix2Pix  
1. Preprocessing: Run the preprocessing script:  
    
   jupyter notebook gan_preprocessing.ipynb  
     
   Ensure it processes images in the combined_dataset2 folder.  

2. Training Pix2Pix:  
   After preprocessing, train the Pix2Pix model:  
 
   jupyter notebook pix2pix.ipynb  
     

CycleGAN  
1. Dataset: Use the image_dataset folder directly.  
2. Training CycleGAN: Run the CycleGAN training script:  
     
   jupyter notebook dip22.ipynb  
     



Evaluation  
To evaluate both models, run the evaluation scripts in their respective notebooks. 
Metrics:  
 PSNR (Peak Signal-to-Noise Ratio)  
 SSIM (Structural Similarity Index Measure)  



Results  

Restoration performance:  
1. Pix2Pix: PSNR = 18.51, SSIM = 0.6838  
2. CycleGAN: PSNR = 32.30, SSIM = 0.8120  

CycleGAN outperforms Pix2Pix in structural preservation and quality restoration.  


