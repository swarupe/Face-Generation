[//]: # (Image Reference)

[image1]: ./assets/processed_face_data.png "Generated Faces"

# Face Generation

## Project Overview

In this project, I defined and trained a DCGAN on a CelebA dataset. The goal of this project is to get a generator network to generate _new_ images of faces that look as realistic as possble.

![Example][image1]


## Project Instruction

### Instruction

1. Clone the repository and navigage to the downloaded folder.
	```
		git clone https://github.com/swarupe/Face-Generation
		cd Face-Generation
	```
2. Open the `dlnd_face_generation.ipynb` file. Of course, you can find HTML version of the file.
	```
		jupyter notebook dlnd_face_generation.ipynb
	```
3. Read and follow the instructions! This repository does not include the dataset of faces. You can find and download it in the notebook.

## Project Information

### Dataset
 * [CelebFaces Attributes Dataset (CelebA)](https://s3.amazonaws.com/video.udacity-data.com/topher/2018/November/5be7eb6f_processed-celeba-small/processed-celeba-small.zip)

### Model - Discriminator
| Layer | Input Dimension | Output Dimension | Batch Normalization|
|-------|-----------------|------------------|-------------|
|Conv1|3|64|False|
|Conv2|64|128|True|
|Conv3|128|256|True|
|Conv4|256|512|True|
|FC|2048|1|False|

### Model - Generator
| Layer | Input Dimension | Output Dimension | Batch Normalization|
|-------|-----------------|------------------|-------------|
|FC|100|2048|False|
|Deconv1|512|256|True|
|Deconv2|256|128|True|
|Deconv3|128|64|True|
|Deconv4|64|3|False|

## Conclusion
DCGAN is one of the most popular and succesful network design for GAN. It mainly composes of convolution layers without max pooling or fully connected layers. It uses strided convolutions and transposed convolutions for the downsampling and the upsampling respectively.