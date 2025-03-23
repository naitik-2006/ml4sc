# Physics Guided Machine Learning on Real Lensing Images

Hello everyone, my name is **Naitik Agrawal**.

Below is a detailed overview of my approach regarding the evaluation task for GSOC.

---

## Overview

### 1.Common Task
For the simple classification task, previous GSOC contributions suggest that various classification models perform similarly , with only minor differences. Based on this, I chose to work with the **EfficientNet** model because it is lightweight and efficient.

### 2. Specific Task 5 (Physics-Guided ML)
For the physics-guided model, I explored two approaches. Ultimately, the second approach (inspired by previous GSOC contributions) worked better.

#### a. Incorporating the Gravitational Lensing Equation in the Loss Function
Initially, I attempted to train a model by incorporating the gravitational lensing equation directly into the loss function. The idea was as follows:
- Using the gravitational lensing equation, we can predict the source (unlensed) image when given an observed (lensed) image.
- My hypothesis was that if the model predicts the source image from the lensed image, and then predicts the source image from that predicted source image, the result should match the original source image.

However, this approach failed significantly. I suspect that my understanding of the physics was not entirely correct, and I am open to feedback on where my assumptions may be mistaken.

#### b. Physics-Informed Features Approach
Inspired by a previous GSOC contributor (SVJLucas), I adopted an approach using a class called `PhysicsInformedFeature` ([link to GitHub repository](https://github.com/ML4SCI/DeepLense/blob/main/Physics_Informed_Transformers_For_Dark-Matter_Morphology_Lucas_Jose/Physics%20Informed%20Features%20For%20Dark%20Matter%20Morphology/examples/example.ipynb)). 

This approach involves:
- Extracting the source image and the gravitational distortion map from the observed image.
- Initially, I attempted to use both the source image and a refined source image (obtained by applying a Sersic profile) for the classification task.
- Due to computational complexity, I eventually opted to use only the source image combined with the original image, applying the same classification approach as in the simple task.

---

## Conclusion

I experimented with these two approaches for the PINN model. While I have a solid background in machine learning, I am still deepening my understanding of gravitational lensing physics. As a result, there may be some inaccuracies in my interpretation of the lensing equations. I welcome any feedback or suggestions on improving my approach.

---
