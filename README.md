# Football-Jersery-Generation-Unconditional_GANS

Overview:
A Unconditional Gan to generate football jerseys. This can be used to augument the ideas of designing new football jersey . This may not be best in producing colourful or artistic jerseys but definitely would generate decent jersey ideas which then can be improved. Involves of creating a generator which takes a latent point and generates a jersey. A discriminator to classify a fake and real image. Gan model which trains the generator in such a way that it can fool the discriminator to generate similar to the original jerseys.  

Dataset Used:

Custom football jerseys from the internet.

Libraries Used :

Keras , Tensorflow, Open CV, Numpy , Matplotlib

Project Flow:

Training and Evaluation:

For every training step in a training loop:

Get a batch of real images -> Train the discriminator on the batch of real images -> Get an equal batch of fake images by generating it from the random latent points and label them as fake samples  -> Train the discriminator on the batch of fake images -> Get random latent points -> Using these random points train GAN model comprising a discriminator and generator where the discriminator is untrainable -> Compute each loss of the training step

Intuition behind GANS for generating jerseys:

The discriminator is trained on equal number of samples from real images and fake images . This enables the discriminator to identify between fake and real images . The generator is used to produce fake images for the training of discriminator with labels as fake. But the same generator is required to fool the discriminator in such a way that the images produced by it are like real images . By doing so we will be able to generate images close to the real ones out of random latent points. Since our data consists of many colourful jerseys as the real images. The generator model has to generate images which are similar to the jerseys , but since its unconditional it can  produce a mix of the jerseys which leads to the ideas for new jersey designs. This is done by training the GAN model which comprises of both the generator and the discriminator, the discriminator is made untrainable . First the generator generates fake images and then the discriminator identifies if it is fake or not . But the trick is this time we pass the label to be real. Obviously the discriminator will detect a fake image as fake but the received label is real , so there is a loss ,hence the GANS model changes its weights in order to produce images which are close to real ones. By repeating the same process over several training steps , finally we will have a generator model which will be able to fool the discriminator by producing real like images.
