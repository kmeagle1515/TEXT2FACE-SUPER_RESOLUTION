# Deep Fusion Generative Adversarial Network

![DFGAN Architecture](assets/FGTD-DFGAN.png)

The architecture of the DFGAN that we have used for training is very similar to the one used by the authors of this network. However, the images generated are of size 128x128. In order to accommodate this reduced image size, the last block of the generator and the discriminator responsible for the generation and validation of 256x256 sized images have been omitted. A matching aware gradient policy was added to the discriminator which helped in improving the quality of the final image. For the DFGAN, the Adam optimizer is set to 𝛽<sub>1</sub> = 0 and 𝛽<sub>2</sub> = 0.9 and the learning rates for the generator and discriminator are 0.0001 and 0.0004 respectively.

---

<img width="1084" alt="image" src="https://user-images.githubusercontent.com/16959405/168946220-5e716eb2-b79a-45a8-b47a-0854d8bb69ce.png">
