# RnDTopics


1. Dirichlet uncertainty and its application to Adversarial and OOD detection 
    * The topic is detection not defence/mitigation . The goal is to use the the uncertainty to detect adversarial attack
        - ON DETECTING ADVERSARIAL PERTURBATIONS - check this paper for the experiments to be conducted 
    * https://github.com/TUM-DAML/dbu-robustness
        - Has implementation of all dirichlet uncertaitny estimation methods
        - http://proceedings.mlr.press/v139/kopetzki21a/kopetzki21a.pdf
        - Good code 
    * [Recent Advances in Adversarial Training for Adversarial Robustness ](https://arxiv.org/pdf/2102.01356.pdf)
        - Adversarial training is considered the best defence for adversarial attack
        - This paper mentions all the different methods and in conclusion mentions the biggest challenges left with AdvTrain
        - Prabhudev looked into adversarial training with Evidential Loss
        - Need new methods.
    * When adversarial training the model accuracy reduces even for evidential loss. 
    * 

2. ~~Uncertainty estimation~~
    * https://github.com/ENSTA-U2IS/awesome-uncertainty-deeplearning
    * Differentiation of all different uncertainty estimation methods
    * TOPIC : All methods have been tested on only MNIST and CIFAR
    * NONE HAS TESTED ON IMAGENET
    * https://github.com/IntelLabs/AVUC/tree/main

3. Label Noise and Dirichlet uncertatinty
    * https://github.com/subeeshvasu/Awesome-Learning-with-Label-Noise#github
    * Inoder to start this RnD you have to train a neural network with the evidential loss function
    * with any of the noisy label dataset
    * compare performance and if the performance is low .
    
    * The goal of the RnD is to find the solution
    * Possible Solutions : Continuous Bernoulli distribution 
       - https://pytorch.org/docs/stable/distributions.html#continuousbernoulli
       - wiki page
    * Dirichlet representation with mean and precision :
        - https://github.com/deebuls/devblog/issues/25
     
   * Code base
        - https://github.com/IntelLabs/AVUC/tree/main

4. ~~Simulated Manipulation with semantic segmentation~~ - Sathwik
    * https://github.com/SeyedHamidreza/cognitive_robotics_manipulation
    * https://github.com/UT-Austin-RPL/GIGA/blob/main/src/vgn/simulation.py
    * We need a scenario (simulated/real) for doing experiments
    * simulation for picking objects using output from semantic segmentation
    * Using pybullet for random scene generation with objects
    * The simulated robot has to use the RGBD and create a grasp pose
    * robot tries to pick the object
    
5. Multi - label uncertatiny quantification
    * For multi label classification scenario how does ue methods perform
    * 

6. ~~Generic normal distirbution loss function for regression~~ Nandhini
   * https://en.wikipedia.org/wiki/Generalized_normal_distribution
   * 2 parameter alpha and beta
   * beta == 2 its normal distirbution
   * beta == 1 its laplace distribution
   * beta < 2 tail heavier than normal
   * beta > 2 tail lighter than normal
   * variance is defined, entropy is defined 
   * 2 options learn both alpha and beta  for all output
   * or learn single beta for a input 
   * or learn single beta for a dataset 
   
7. ~~Surface normal uncertainty~~ Kaushik
   - Datasets Nyuv2 and scannet
   - dataset available - https://github.com/xjqi/GeoNet
   - https://github.com/hjwdzh/framenet/tree/master/src
   - comparison code - https://github.com/baegwangbin/surface_normal_uncertainty
   - All code available , replace loss with wrapped cauchy 
   - Most probably the error shall reduce 

8. Continuous Bernoulli distribution 
       - https://pytorch.org/docs/stable/distributions.html#continuousbernoulli
       - wiki page
       - Loss function using continuous Bernoulli distirbution 
       - Not clear need to rethink

9. ~~Conditional regression/classification (Multi input regression/classification)~~ Gokul
   - In addition to the input image we an add context informtion of task as embeddings
   - For example for object pickpoint regression task which outputs only single object center point
   - If we add the name of the object as input then we can select which center we are looking
   - To compare :
      - How to embedd the object name ? Fixed embdding (ECOC embedding) vs learned embedding ? If learned then how ?
      - Fusion which ? Where to fuse, channel fusion vs layer fusion,
   - Real world or simulation execution

10. Leaner convolution application to embedded systems and uncertainty estimation
    - https://link.springer.com/chapter/10.1007/978-3-031-27440-4_41
    - Jeon et al. [6] notice, with a hardware implementation, that depthwise convolution is more time-consuming than point convolution. 
    - https://gitlab.emse.fr/b.nguyen/primitive_of_convolution
    - Addconvolution from AdderNet: Do We Really Need Multiplications in Deep Learning? : the code from the official repository is adpated in tensorflow.
    - Shiftconvolution from Constructing Fast Network through Deconstruction of Convolution : implementation taken from the official repository.
       
# Deep learning projects

1. Regression loss vs classification loss impact on adversarial attack
   - loss functions : softmax vs binary cross entropy vs mse vs l1
   - embedding : one hot vs error correction 
      - Use foolbox and do adersarial attack
   - datasets : cifar 100 , traffic ign
   - segmentation voc 
   - open problem : convertin regression output to classification classes 
2. ECOC embedding with radial encoding for regression learning
   - ECOC onverts one hot to hadmards code
   - Hadards code needs to be longer than the one hot encoding
   - Can we encode the classification problem with regression outputs
   - How will be encode : One radial values 0 to 2pi 
   - Equally Divide 0 to 2pi with repsect to number of classes
   - Use the Radial loss function of gaussian or laplace 
   - How many embedding is required?
   - Datasets : higher number of classes cidar 100 or german traffic
   - Again comparison with classification loss for adversarial attack performance 
   - ood performance
   - 
3. Hufmann coding or arithmetic coding 
   - Huffman coding or arithmetic coding is done for loselss compression based on the probability of the data
   - So most probable data is encoded with less bits and high probable data is represented with high bits
   - The technique can be applied to based on the confussion of classes
   - So the lesat confusion class can be given less bits 
   - and most confussing classes get large bits 
   - The idea is that based on the encoding since the most confusing class share most bits except one, based on the decoding we can sure that the class is one of the both but not sure which .
   
1. Does multiple layer loss improves training ?
   - Currently we only use loss is calculated using the last layer and labels.
   - We can add fc layer at different levels and calculate loss at different levels
   - Does adding such losses improve the performance?
   - Is it true also for UC evidential loss?
      - Is the loss decreasing at each level ? as more layers is added it should learn more
      - Does this have an impact on reliability, adversarial attack 
      - Can this be used for OOD
   - How to combine the different loss (average or weighted average)?
   - For semantic segmentation on can use the upsample o/p  and generate these losses as in paper: Multiview deep learning for consistent semantic mapping with RGB-D cameras.
   - For semantic segmentation : How to reduce the label to different sizes:
       - Convert image to one-hot-label
       - Use max pooling to reduce the shape 
       - This will make sure in the redcued image pixel - All the values of the above pixel exist. 
       - 
