# Bibliography with notes
My bibliography for different fields with some annotations

## Deep Learning

### Superresolution
1. "Image Super-Resolution Using Deep Convolutional Networks", Dong et al. http://mmlab.ie.cuhk.edu.hk/projects/SRCNN.html . Very simple CNN topology for superresolution. Only convolutions are used.
2. "Accurate Image Super-Resolution Using Very Deep Convolutional Networks" Kim et al. http://arxiv.org/abs/1511.04587 . Single-image superresolution. Some tricks are presented to improve the quality. Depth is increased to 20 layers. Residual training is used to improve the output (input is transferred to the output and added to the output of the network, a great idea). Gradient clipping and high learning rates.
3. "Multi-Frame Video Super-Resolution Using Convolutional Neural Networks" http://cs231n.stanford.edu/reports2016/212_Report.pdf . Networks for superresolution using single-image or multi-frame. Some interesting tricks for regularizing the training.
4. "Real-Time Single Image and Video Super-Resolution Using an Efficient Sub-Pixel Convolutional Neural Network", Wenzhe Shi, Jose Caballero, Ferenc Huszar, Johannes Totz, Andrew P. Aitken, Rob Bishop, Daniel Rueckert, Zehan Wang http://www.cv-foundation.org/openaccess/content_cvpr_2016/html/Shi_Real-Time_Single_Image_CVPR_2016_paper.html . A single-image superresolution is proposed. As opposed to previous approaches, the network input is the low resolution image, which is then transferred through several convolutional layers, and a final sub-pixel convolution with appropriate learnt kernels is used to generate the high-resolution image. This improves previous results in terms of speed and quality because the standard bilinear interpolation used in the first layer is substituted by trained kernels. Makes lots of sense.

### Generative adversarial network
1. "Generative Adversarial Networks", Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, Yoshua Bengio https://arxiv.org/abs/1406.2661. Proposal of the new framework to build generative models, in this case in 1D.
2. "Semantic Image Inpainting with Perceptual and Contextual Losses", Raymond Yeh, Chen Chen, Teck Yian Lim, Mark Hasegawa-Johnson, Minh N. Do https://arxiv.org/abs/1607.07539. A Deep Convolutional Generative Adversarial Network is proposed for inpainting.
3. Blog post showing some ideas of generative adversarial models. https://openai.com/blog/generative-models/
4. Blog post showing image inpaiting using a DCGAN, with code in Tensorflow https://bamos.github.io/2016/08/09/deep-completion/

### To-Do
1. Estimate Local Correlation Tracking at several heights in the atmosphere starting from two or more consecutive images. Several possibilities can be used:
    a. Use simulations and a converging CNN and then another divergent to go back to the full map (http://arxiv.org/abs/1601.07532) (http://arxiv.org/abs/1305.6033v1)
    b. Use simulations and a CNN made only of convolutions (no pooling) that keeps the sizes of the layers equal to that of the input.
2. DNN for phase diversity. Input is two images, one focused and the other one defocused. The output is the reconstructed image. Trained on simulations with many PSFs. Probably the best is a pure convolutional network with many layers which keeps the same output size as the input. This also makes it applicable to images of arbitrary size. Probably good to propagate focused input to the end and train only on the residual. *Can we also output the Zernike coefficients of the wavefront?*
3. Probabilistic He 10830 inversions. *Test sizes and topologies*
4. Probabilistic Milne-Eddington inversions for Big Bear Solar Observatory 15648 A.
5. Fe I inversions using horizontal patches to add some spatial information. Trained on simulations?
6. Filament detection or detection of structures in magnetograms 
7. Detección de filamentos o detección de estructuras en magnetogramas http://arxiv.org/abs/1505.04597 and https://github.com/jocicmarko/ultrasound-nerve-segmentation
8. HMI superresolution starting from simulations and/or SST http://arxiv.org/abs/1511.04587v1.pdf
9. Generate synthetic images of the Sun using Convolutional Generative Adversarial Networks. Potentially, one could even generate 3D simulations

### Tricks
DUNA
source to_theano -> to use Theano
source to_tensorflow -> to use Tensorflow

PYTHON INSTALLATION
conda install numpy scipy h5py ipython matplotlib 
pip install keras pydot-ng graphviz