## To-Do
1. (IN PROGRESS) Estimate Local Correlation Tracking at several heights in the atmosphere starting from two or more consecutive images. Several possibilities can be used:
    a. Use simulations and a converging CNN and then another divergent to go back to the full map (http://arxiv.org/abs/1601.07532) (http://arxiv.org/abs/1305.6033v1)
    b. Use simulations and a CNN made only of convolutions (no pooling) that keeps the sizes of the layers equal to that of the input.
    c. U-net
2. DNN for phase diversity. Input is two images, one focused and the other one defocused. The output is the reconstructed image. Trained on simulations with many PSFs. Probably the best is a pure convolutional network with many layers which keeps the same output size as the input. This also makes it applicable to images of arbitrary size. Probably good to propagate focused input to the end and train only on the residual. *Can we also output the Zernike coefficients of the wavefront?*
3. (IN PROGRESS) Probabilistic He 10830 inversions. *Test sizes and topologies and dropout Bayesian output*
4. (IN PROGRESS) Probabilistic Milne-Eddington inversions for Big Bear Solar Observatory 15648 A.
5. Fe I inversions using horizontal patches to add some spatial information. Trained on simulations?
6. Filament detection or detection of structures in magnetograms 
7. Detección de filamentos o detección de estructuras en magnetogramas http://arxiv.org/abs/1505.04597 and https://github.com/jocicmarko/ultrasound-nerve-segmentation
8. HMI superresolution starting from simulations and/or SST http://arxiv.org/abs/1511.04587v1.pdf
9. Generate synthetic images of the Sun using Convolutional Generative Adversarial Networks. Potentially, one could even generate 3D simulations
10. Atmosphere tomography using CNN? S-DIMM?
11. Prediction of the activity on the Earth using CNN. Take images (magnetograms, images, etc.) and predict whether activity measured at Earth is going to happen (K-index, as-index or activity at L1). https://arxiv.org/abs/1411.1405, http://iopscience.iop.org/article/10.3847/0004-637X/829/2/89/meta