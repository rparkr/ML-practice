# Deep learning, class projects
A collection of PyTorch projects I completed for my Computer Science 474: Intro to Deep Learning course at Brigham Young University, Jan-Apr 2022.

The projects generally progress through developments in the field of deep learning: starting with simple Fashion MNIST classifiers, progressing to convolutional networks, image segmentation, style transfer, RNNs and LSTMs, Transformer sequence-to-sequence translation and language modeling, GANs for image generation, and basic reinforcement learning.

Each project is a Jupyter notebook file (.ipynb) that I ran in Google Colab for access to free GPUs. The project objectives and many of the code outlines were provided as part of the course, but I often wrote my own procedures in addition to the ones given so I could practice different ways of accomplishing objectives and broaden my understanding of deep learning methods.

## Projects
1. [Fully-connected linear network for classifying Fashion MNIST](Project_1_Linear_Net_Fashion_MNIST.ipynb)
2. [Convolutional network for classifying Fasion MNIST](Project_2_Convolutional_Net_Fashion_MNIST.ipynb)
3. [U-Net convolutional network for pixel-level image segmentation](Project_3_U-Net_image_segmentation.ipynb), used to label images of tissue biopsies with a binary classification mask (cancerous or non-cancerous)
4. [Style transfer using pre-trained VGG-19 network](Project_4_Style_transfer.ipynb). The goal was to extract feature maps from layers in the VGG vision network to combine the content of one image with the style of another image.
 * ![Content, style, and generated image](https://github.com/rparkr/ML-practice/blob/main/Deep%20learning/Class%20projects/imgs/Style_transfer.png)
 * **Example output** 
 * <img src="https://github.com/rparkr/ML-practice/blob/main/Deep%20learning/Class%20projects/imgs/Style_transfer.gif" width=300>
5. [Character-level language modeling using a Recurrent Neural Network](Project_5_Recurrent_Net_language_model.ipynb). The implementation includes RNNs with the Long Short-term Memory (LSTM) structure and RNNs with the Gated Recurrent Unit (GRU) structure.
6. [Sequence-to-Sequence text translation using an encoder-decoder Transformer network](Project_6_Transformer_Net_seq2seq.ipynb). Follows the implementation of the Transformer model architecture from "Attention is All You Need" (Vaswani et al. 2017). Translates sentence pairs from Spanish to English.
7. [Image generation using a Generative Adversarial Network](Project_7_GAN_image_generation.ipynb). This project uses a simple, 25M-parameter convolutional GAN to generate images that resemble images it was trained on. It implements training across two image domains: the CelebA dataset (generates images of human faces) and a custom dataset of images of vehicles.
8. [Transfer learning: fine-tuning a ResNet image classifier and a GPT-2 language model on custom datasets](Project_8_Transfer_learning.ipynb)
9. [Reinforcement learning using DQN and PPO networks](Project_9_Reinforcement_learning.ipynb). In this project, I train a Deep Q Network (DQN) and a Proximal Policy Optimization network (PPO) to solve the cartpole problem using OpenAI's `gym` package. The goal of the cartpole problem is to teach the network how to balance a pole mounted at the middle of a cart by moving the cart horizontally, left and right.
