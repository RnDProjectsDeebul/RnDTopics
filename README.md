# RnDTopics


1. Dirichlet uncertainty and its application to Adversarial and OOD detection
    * http://proceedings.mlr.press/v139/kopetzki21a/kopetzki21a.pdf
    * https://github.com/TUM-DAML/dbu-robustness
    * Has implementation of all dirichlet uncertaitny estimation methods
    * Good code 

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
    * We need a scenario (simulated/real) for doing experiments
    * simulation for picking objects using output from semantic segmentation
    * Using pybullet for random scene generation with objects
    * The simulated robot has to use the RGBD and create a grasp pose
    * robot tries to pick the object

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
