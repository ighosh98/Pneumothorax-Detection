# Pneumothorax-Detection
Repository for code tested to build models for the Kaggle SIIM-ACR Pneumothorax Segmentation contest.

Managing DICOM images: Tips and tricks for the radiologist
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3354356/

CheXNeXt PLOS article
https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002686

CheXNet: Radiologist-Level Pneumonia Detection | Kaggle
https://www.kaggle.com/ashishpatel26/chexnet-radiologist-level-pneumonia-detection

Original CheXNet arxiv article
https://arxiv.org/abs/1711.05225

Chester: A Web Delivered Locally Computed Chest X-Ray Disease Prediction System
https://arxiv.org/abs/1901.11210

Google AI algorithm may improve chest x-ray interpretation, radiologist efficiency
https://www.healthimaging.com/topics/artificial-intelligence/google-ai-algorithm-may-improve-chest-x-ray-interpretation

Thoracic Disease Identification and Localization with Limited Supervision
https://arxiv.org/abs/1711.06373

Pneumothorax detection with CheXNet: 
* A binary classification problem.
* CheXNet is a 121-layer Dense Convolutional Network (DenseNet) trained on the ChestX-ray 14 dataset. 
* DenseNets improve flow of information and gradients through the network, making the optimization of very deep networks tractable. 
* The final fully connected layer is replaced with one that has a single output, after which we apply a sigmoid nonlinearity. (we can consider using a final SVM layer?) 
* The weights of the network are initialized with weights from a model pre-trained on ImageNet (Deng et al., 2009).
* The network is trained end-to-end using Adam with standard parameters (β1 = 0.9 and β2 = 0.999) (Kingma & Ba, 2014). 
* The model was trained using mini batches of size 16. 
* An initial learning rate of 0.001 that is decayed by a factor of 10 each time the validation loss plateaus after an epoch. 
* The model with the lowest validation loss was picked. 
* Can add to our detection mechanism Sobel edge detection or operator(s): https://www.sciencedirect.com/topics/engineering/sobel-operator
* Assume no patient overlap between the training and testing datasets. 
* Pathologies covered:
    1. Atelectasis
    2. Cardiomegaly
    3. Effusion
    4. Infiltration
    5. Mass
    6. Nodule
    7. Pneumonia
    8. Pneumothorax
    9. Consolidation
    10. Edema
    11. Emphysema
    12. Fibrosis
    13. Pleural Thickening
    14. Hernia
* CheXNet detection accuracy = 0.8887 (2017) 
* Possible use case for NASNet. Currently inserted Keras' default NASNET into the model. Have a look at the architectures mentioned here: https://towardsdatascience.com/illustrated-efficient-neural-architecture-search-5f7387f9fb6#df67
* Will look into Reinforcement Learning for an effective implementation of ENAS.


UNet Tutorials
- https://www.youtube.com/watch?v=E1Y8HZcpm-I
- https://www.youtube.com/watch?v=M3EZS__Z_XE
- https://www.youtube.com/watch?v=nG3tT31nPmQ
- https://www.youtube.com/watch?v=cm6GmGkbhBo
