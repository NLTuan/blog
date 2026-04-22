Title: Diffusion Transformer from scratch
Date: 2026-04-21
Category: Technical
Tags: models, research
Author: Le Tuan Huy (Tony) Nguyen
Summary: Custom implementation of Diffusion Transformer from scratch

# Diffusion Transformer from scratch

In my journey of understanding the state of the art in end to end robotic policy training, I found a very very common paradigm that
a lot of research labs have converted to which is to pivot towards diffusion-based models to model action chunks for robots to perform(DIFFUSION POLICY REF, PI 0 REF). Many of you reading are probably familiar with diffusion models in the context of image generation, and robot training policies are merely borrowing these same architectures. Initially, diffusion models were CNN based, but with the rise of transformers, they have found their way to sneak in as well: Enter the Diffusion Transformer. I have bestowed upon myself the task of reimplementing the paper that has introduced this architecture: Scalable Diffusion Models with Transformers (REF FOR DIFFUSION TRANSFORMER). In this paper, they showed that Diffusion Transformers had scalability properties and outperformed all prior diffusion models. For this implementation, I will be staying within the image generation space. (Pi 0 implementation coming soon!)

The implementation of Diffusion Transformer will be split into it's constituent parts as Pytorch modules and then assembled as one DiT module. The parts consist of: Patchify, Conditionning Embeddings, DiT Block with adaLN-Zero, and output projection layers.

However, the paper does not include the VAE that compresses the original image into a latent representation and instead opts into using a frozen pretrained VAE. This VAE allows the Diffusion Transformer to work in a smaller dimension, which reduces computational costs and makes training efficient.

# Patchify
In order for Transformers to operate on images, we need to ensure that the images are of the shape that Transformers love, which look like a sequence of tokens with an embedding/hidden dimension (e.g. (batch, seq_len, dim)). However, images are of the shape (batch, channels, height, width). This can be changed by applying a `Conv2d` layer followed by a `reshape`. The `Conv2d` layer allows us to regroup squares of pixels into patches which get treated like tokens later on in the attention operations. Also, it allows for variable patch sizes, bigger patches will yield less "tokens", thus reducing compute complexity. For example, for a latent of shape (4, 32, 32), a patch size of 2, a `Conv2d(4, 1152, patch_size, patch_size)`, passing the latent through the convolutional layer yields an output of shape (4, 1152, 16, 16). This is not the desired shape yet, and a `reshape` operation must be applied. Calling `einsum.reshape(latent, 'b d h w -> b (h w) d')` flattens the height and width dimension and puts the hidden dimension to the end, yielding something similar to that of an embedded token sequence. Now, this tranformed latent representation can undergo attention operations





# References

