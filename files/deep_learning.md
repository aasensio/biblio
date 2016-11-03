## Deep Learning

### Probabilistic output of NN (Bayesian)
1. Interesting idea of using dropout during training and testing phase to compute the probability of outputs http://www.computervisionblog.com/2016/06/making-deep-networks-probabilistic-via.html , http://mlg.eng.cam.ac.uk/yarin/blog_3d801aa532c1ce.html
2. Dropout layers are only used in Keras in training phase. However, they can be always used if used inside a Lambda layer: 
```
Lambda(lambda x: K.dropout(x, 0.2)))
```

### Superresolution
1. "Image Super-Resolution Using Deep Convolutional Networks", Dong et al. http://mmlab.ie.cuhk.edu.hk/projects/SRCNN.html . Very simple CNN topology for superresolution. Only convolutions are used.
2. "Accurate Image Super-Resolution Using Very Deep Convolutional Networks" Kim et al. http://arxiv.org/abs/1511.04587 . Single-image superresolution. Some tricks are presented to improve the quality. Depth is increased to 20 layers. Residual training is used to improve the output (input is transferred to the output and added to the output of the network, a great idea). Gradient clipping and high learning rates.
3. "Multi-Frame Video Super-Resolution Using Convolutional Neural Networks" http://cs231n.stanford.edu/reports2016/212_Report.pdf . Networks for superresolution using single-image or multi-frame. Some interesting tricks for regularizing the training.
4. "Real-Time Single Image and Video Super-Resolution Using an Efficient Sub-Pixel Convolutional Neural Network", Wenzhe Shi, Jose Caballero, Ferenc Huszar, Johannes Totz, Andrew P. Aitken, Rob Bishop, Daniel Rueckert, Zehan Wang http://www.cv-foundation.org/openaccess/content_cvpr_2016/html/Shi_Real-Time_Single_Image_CVPR_2016_paper.html . A single-image superresolution is proposed. As opposed to previous approaches, the network input is the low resolution image, which is then transferred through several convolutional layers, and a final sub-pixel convolution with appropriate learnt kernels is used to generate the high-resolution image. This improves previous results in terms of speed and quality because the standard bilinear interpolation used in the first layer is substituted by trained kernels. Makes lots of sense.

### Deconvolution and image correction
1. "Compression artifacts removal using CNN" http://wscg.zcu.cz/wscg2016/full/F71-full.pdf . Interesting approach to removing JPEG compression artifacts. They use fully convolutional CNN, made only of convolutional layers and ReLU. They use residual learning, appropriate for networks for which the input and the output are very similar, so that learning the difference makes more sense. They also introduce some regularization in the loss function to emphasize edges. The Sobel filters can be implemented as a convolutional layer with fixed kernels. They also describe tricks for weight initialization and using skip (the activation of first convolution layer is passed to deeper layers, merged as an addition or as a concatenation, inspired by "Fully convolutional networks for semantic segmentation" Long et al. 2015).
2. "CNN for license plate motion deblurring" https://arxiv.org/abs/1602.07873 . Fully convolutional (no pooling) for license plate deblurring.
3. "CNN for direct text deblurring" http://www.fit.vutbr.cz/~ihradis/CNN-Deblur/ and also http://www.fit.vutbr.cz/~ihradis/pubs.php?file=%2Fpub%2F10922%2FHradis2015_CNN_deblurring.pptx&id=10922

### Generative adversarial network
1. "Generative Adversarial Networks", Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, Yoshua Bengio https://arxiv.org/abs/1406.2661. Proposal of the new framework to build generative models, in this case in 1D.
2. "Semantic Image Inpainting with Perceptual and Contextual Losses", Raymond Yeh, Chen Chen, Teck Yian Lim, Mark Hasegawa-Johnson, Minh N. Do https://arxiv.org/abs/1607.07539. A Deep Convolutional Generative Adversarial Network is proposed for inpainting.
3. Blog post showing some ideas of generative adversarial models. https://openai.com/blog/generative-models/
4. Blog post showing image inpaiting using a DCGAN, with code in Tensorflow https://bamos.github.io/2016/08/09/deep-completion/

### Deep Reinforcement Learning
1. Blog post on RL http://karpathy.github.io/2016/05/31/rl/
2. Extension of RL to continuous variables https://arxiv.org/abs/1509.02971
3. Example of continuous RL for car driving in Keras https://yanpanlau.github.io/2016/10/11/Torcs-Keras.html
4. Example of discrete RL https://yanpanlau.github.io/2016/07/10/FlappyBird-Keras.html

### Fully convolutional networks
1. Undecimated fully convolutional networks. Interesting approach to get rid of pooling in fully convolutional networks https://arxiv.org/abs/1508.00317v1 . Also used here: https://arxiv.org/abs/1511.07122
2. Getting rid of artifacts in upconvolutions. It's much better to just upsampling (juts simple resizing using nearest neighbor) and then apply a standard convolutional layer: http://distill.pub/2016/deconv-checkerboard/

### LSTM
1. http://colah.github.io/posts/2015-08-Understanding-LSTMs/