# Self-directed project: Full-page handwriting recognition
Apr-2022

This was my final project for my CS 474: Intro to Deep Learning course taken at Brigham Young University from Jan-Apr 2022.

🚧 This model is still a work in progress. See notes below on planned next steps. 🚧

**Objective:** train a neural network to extract the text from images of full pages of handwritten text.

**Purpose:** use the trained network to transcribe ~650 pages of handwritten text that I recorded in journals from May-2013 to Apr-2015 while serving as a volunteer representative for The Church of Jesus Christ of Latter-day Saints in Mexico City, Mexico.

Each journal page has over 500 words, so the entire collection has over 325,000 words. At a speed of about 45 words per minute, manually transcribing the journal pages would take over 7,200 minutes, or 120 hours. Adding the time to photograph all 600 pages (which takes roughly 45 seconds per page, or 7.5 hours total), the entire manual transcription process could take over 3 work weeks of time to complete. This neural network would drastically reduce the transcription time while simultaneously increasing accuracy (hopefully).

## Files
The `notebooks` folder has Jupyter notebooks that I used throughout this project. See [4_Full-page-HTR_Neural_Network.ipynb](https://github.com/rparkr/ML-practice/blob/main/Deep%20learning/Full%20page%20handwritten%20text%20recognition/notebooks/4_Full-page-HTR_Neural_Network.ipynb) for my model.

The notebooks are listed in the order I followed for this project. That is, the first notebook has various ideas of challenges to solve using neural networks; the second one generates training images; the third one processes the images, tests augmentation methods, and begins the neural network; and the fourth one has the complete neural network, assuming the data is already available (I stored my data in Google Drive and accessed it through Google Colab while running the model).

## Overview
For this project, I implemented the network architecture used by Singh et al. in ["Full Page Handwriting Recognition via Image to Sequence Extraction" (2021)](https://paperswithcode.com/paper/full-page-handwriting-recognition-via-image). My network is adapted from [Tobias van der Werff's implementation](https://github.com/tobiasvanderwerff/full-page-handwriting-recognition), with modifications to suit my dataset and training requirements.

The network combines a ResNet encoder and a Transformer decoder. The ResNet vision model embeds input images into a feature space that the decoder attends to when predicting the next token in a sequence. The model is trained using teacher forcing, where the decoder receives the actual previous tokens in the sequence as its input. When used for inference, the decoder uses as input its previous output tokens.

The decoder uses a character-level vocabulary, where each token in a sequence is a single character.

**Model architecture**, taken from pg. 4 of Singh et al. (2021).

<img src="https://github.com/rparkr/ML-practice/blob/main/Deep%20learning/Full%20page%20handwritten%20text%20recognition/imgs/Model-Architecture_FPHR_Singh-et-al_2021.png" width="600">


## Data prep
This model aims to tackle the challenge of _offline_ handwritten text recognition (HTR), where _offline_ means that no stroke information is available, only an image of the handwritten text. In contrast, _online_ HTR means that stroke information is available, which can be generated from a device with a digital stylus pen.

Since neural networks require large amounts of data for training, I generated a dataset of 10,000 images of full-page text that resemble pages of my journals. That's still a small dataset for a neural network, but it is at least enough to produce results as a proof-of-concept.

I also preprocessed the images (e.g., binarized them so each pixel is either black or white) and applied augmentations during training so the model becomes more robust.

**Example images:**

Two pages from one of my journals: 
* <img src="https://github.com/rparkr/ML-practice/blob/main/Deep%20learning/Full%20page%20handwritten%20text%20recognition/imgs/journal_page.jpeg" width="800">

Journal page after processing:
* <img src="https://github.com/rparkr/ML-practice/blob/main/Deep%20learning/Full%20page%20handwritten%20text%20recognition/imgs/processed_img.jpeg" width="600">

Generated image after processing:
* <img src="https://github.com/rparkr/ML-practice/blob/main/Deep%20learning/Full%20page%20handwritten%20text%20recognition/imgs/generated_img_binary.png" width="600">

Generated image with augmentations (applied during model training):
* <img src="https://github.com/rparkr/ML-practice/blob/main/Deep%20learning/Full%20page%20handwritten%20text%20recognition/imgs/generated_img_augmented.png">


## Notes
🚧 This model is still a work in progress. In particular, it has a memory leak during model training, where CPU RAM usage increases even though the model trains on the GPU. Also, the model performs extremely slowly at inference time, perhaps because of the token-by-token loop through 3,500 characters (roughly the maxiumum number of characters on a page from my journal).

## What I've learned
I experimented with implementing a state-of-the-art model from Singh et al., one of the only models to tackle full-page handwriting recognition. Thanks to Tobias van der Werff for the excellent implementation of the neural network described by Singh et al., I learned about 1D and 2D positional encoding, input sequence masking for training a model using the teacher-forcing technique, and how to adapt PyTorch's modular Transformer and ResNet models to a particular task.

I also learned much about creating custom datasets for PyTorch models, image preprocessing, Torchvision transforms for image augmentation, memory management, gradient accumulation when batch sizes are constrained, and saving model checkpoints.
