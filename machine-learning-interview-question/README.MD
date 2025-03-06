### Machine Learning Interview Question

1. Can you explain the difference between supervised, unsupervised, and reinforcement learning?
    - Supervised Learning
        - Definition: The model is given data with label.
        - Common Algorithms: Linear Regression, Decision Trees, Random Forest, Neural Networks.
    - Unsupervised Learning
        - Definition: The model is given data without label. It must find patterns or structures on its own.
        - Common Algorithms: K-Means Clustering, Principal Component Analysis (PCA), Autoencoders.
    - Reinforcement Learning
        - Definition: An agent learns by interacting with an environment and receiving rewards or penalties for actions taken. The goal is to maximize cumulative rewards.
        - Common Algorithms: Q-Learning, Deep Q Networks (DQN), Proximal Policy Optimization (PPO).

2. How to Prevent Overfitting?
    - More Data: Increasing the size of the dataset
    - Regularization: L1 (Lasso) and L2 (Ridge) regularization penalize overly complex models, avoid over-reliance on specific features or patterns in the training data. Eventually, helping to get a balance between fitting the training data well and generalizing it well on unseen/ new data.
    - Dropout (for Neural Networks): Randomly dropping neurons during training, it forces the network to learn more robust features.
    - Early Stopping: Stop training when validation performance stops improving to prevent overfitting.
    - Cross-Validation: Using k-fold cross-validation ensures the model is evaluated on different subsets of data.
    - Data Augmentation: Increases training data by applying transformations (e.g., flipping, rotating images in computer vision).
    - Simpler Model: Reducing the complexity of the model (fewer layers in deep learning, fewer parameters in traditional ML models) can prevent overfitting.

3. Model Deployment?
