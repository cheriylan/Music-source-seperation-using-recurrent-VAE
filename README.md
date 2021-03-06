# Musical Source Separation using Deep Recurrent Variational Autoencoder

>* [__Take a look at the demo!__](https://www.youtube.com/)

## Intro
Traditionally, discriminative training for musical source separation is proposed using deep neural networks or non-negative matrix factorization. In this project i proposed a variational autoencoder (VAE) based framework using recurrent neural networks for blind musical source (bass,drums ,vocals and others) separation. It is principled generative model compared to other traditional discriminative models.

Variational auto encoder structure[ Fig ] <img src="img/vae.PNG">
                         


## What is Recurrent VAE for Music Source Separation?
The Recurrent VAE for Music Source Separation is a recurrent neural network variational autoencoder decder architecture that operates on magnitude spectrum of the mixed music and generates seperated musical sourses (bass,drums, vocals and etc).

Flow of the model [ Fig ]  <img src="img/brief.PNG">
  

The encoder structure is actually taken from goolge's Music-VAE architecture,It uses a two-layer bidirectional
LSTM network (Hochreiter & Schmidhuber, 1997; Schuster & Paliwal, 1997). It process an input music sepectogram 
x = {x1, x2, . . . , xL } to obtain the final state vectors from the second bidirectional LSTM layer. These
are then concatenated and fed into two fullyconnected layers to produce the latent distribution parameters µ and σ.

The decoder structure is a simple uni-directinal two-layer LSTM network with tensorflows seq2seq encoders.


Model architecture[ Fig ]  <img src="img/structure.PNG">
  
                            
* I used DSD100 [__Dataset__] (https://sigsep.github.io/datasets/dsd100.html) for training my model

## Requirements
* Numpy >= 1.3.0
* TensorFlow == 1.2
* librosa == 0.5.1

## Usage
* Training
  * ```python train.py```
  * check the loss graph in Tensorboard.


