# Facial-Reconstruction-of-Masked-Face-using-GAN

## Why
With the advent of COVID-19 facial coverings like masks have become increasingly prevalent. Even though advanced facial recognition systems have been developed and produce satisfactory results, obstructions and covering on facial features is a major issue thatrender these systems useless. Since mask is one of the things that can be classified as obstruction to a face, we developed project that removes the mask and generates or reconstructs the hidden part of the face covered by mask.

## Who
It was developed by [Arpita Nanda](https://github.com/ArpitaNanda "Arpita Nanda"), [Dawood Damda](https://github.com/Dawood-Damda "Dawood Damda"), [Gagan V](https://github.com/gaganmarvel "Gagan V"), Emaad Jaffer

## Methodology 
We developed a model using two main modules:
- Map Module, a modified version of the U-Net, it creates a segmentation map of the mask.
- Editing Module, composed of GAN(one generator and two discriminator) and a Perceptual Network, it generates the hidden part of the face covered by mask.

This project will take all the required images the model needs (masked images) from the directory testing/test_mask. First, it will generate the maps from the masked images and will save them in testing/test_map. Then, it uses these maps for the editing module, and it generates the unmasked images, saved in testing/results.
 
## How to run the project
- Download or clone this repository.
- Download the [Dataset](https://drive.google.com/drive/folders/1yPjANI3pCgd6SQ0_WX7I38QiUxuQk34U?usp=sharing "Training and testing dataset").
- Run `Unmask.ipynb`
- To skip the training process, you can download the pre-trained model from [Checkpoints](https://drive.google.com/drive/folders/1YJCCpV4UyyXlfvPrEYQvVUQzG9NtOcH6?usp=sharing "Pre-trained model").

## Results
After the training process, accuracy and loss graphs were plotted.

![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/Accuracy%20and%20Loss/Segmentation%20model%20accuracy.png "Model Accuracy")  ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/Accuracy%20and%20Loss/Segmentation%20model%20accuracy.png "Model Loss")

Check out 'Facial Reconstruction of Masked Face Using Generative Adversarial Networks.pdf' for more detailed explanation about the project.

Here's some sample outputs:

------------------Input--------------------------Mask Segmentation---------------------Generated Output---------

![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/mask/000000.png) ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/map/000000.png.jpg) ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/result/000000.png.jpg )

![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/mask/000002.png) ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/map/000002.png.jpg) ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/result/000002.png.jpg)

![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/mask/000003.png) ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/map/000003.png.jpg) ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/result/000003.png.jpg)

The ground truth images for above examples:

![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/no_mask/000000.png) ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/no_mask/000002.png) ![alt text](https://github.com/gaganmarvel/Facial-Reconstruction-of-Masked-Face-using-GAN/blob/main/examples/no_mask/000003.png)

As you can see, even with the few resources we had, the outcomes are still more than adequate. Overfitting of the model can be seen, which results in poor generalisation. The issue might have been resolved by making the dataset more diverse and heterogeneous.

## NOTE: 
We recommend you to use system with higher processor, higher RAM and a better GPU for smooth training and processing. 
or
Use `Google Colab Pro` to avoid "ResourceExhaustedError" error during the training process due to insufficient RAM.
