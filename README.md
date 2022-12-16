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

2. Uncertainty estimation 
    * https://github.com/ENSTA-U2IS/awesome-uncertainty-deeplearning
    * Differentiation of all different uncertainty estimation methods
    * TOPIC : All methods have been tested on only MNIST and CIFAR
    * NONE HAS TESTED ON IMAGENET

3. Label Noise and Dirichlet uncertatinty
    * https://github.com/subeeshvasu/Awesome-Learning-with-Label-Noise#github
    * Inoder to start this RnD you have to train a neural network with the evidential loss function
    * with any of the noisy label dataset
    * compare performance and if the performance is low .
    * The goal of the RnD is to find the solution

4. Simulated Manipulation with semantic segmentation
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

6. Generic normal distirbution loss function for regression
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
   
# Deep learning projects

1. Does multiple scale loss improves training ?
   - Currently we only use loss is calculated using the last layer and labels.
   - We can add fc layer at different levels and calculate loss at different levels
   - Does adding such losses improve the performance?
   - Is it true also for UC evidential loss?
      - Is the loss decreasing at each level ? as more layers is added it should learn more
      - Does this have an impact on reliability, adversarial attack 
      - Can this be used for OOD
   - How to combine the different loss (average or weighted average)?
   - For semantic segmentation on can use the upsample o/p  and generate these losses as in paper: Multiview deep learning for consistent semantic mapping with RGB-D cameras.
