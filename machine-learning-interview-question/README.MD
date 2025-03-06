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
    - Step 1: Model Training & Evaluation
        - Train the model by using dataset.
        - Evaluate its performance using test dataset (accuracy, precision, recall, etc.).
        - Save the trained model in format (ONNX, Pickle, etc)
    - Step 2: Containerization & Packaging
        - Use Docker to containerize the model, ensuring it runs consistently across environments.
        - Example: Create a Flask or FastAPI service to expose the model as a REST API in Docker
    - Step 3: Model Hosting & Deployment
        - Deploy on cloud platforms (AWS, GCP, Azure) or on-premise servers.
        - Use Kubernetes and Seldon Core for scalable and efficient deployment.
        - Serve the model with TensorFlow Serving, TorchServe, or MLflow.
    - Step 4: Monitoring & Logging
        - Implement monitoring to track latency, prediction accuracy, and model drift.
        - Utilize tools like Prometheus, Grafana, or ELK Stack for logging and alerts.
    - Step 5: Scaling & Load Balancing
        - Use autoscaling with Kubernetes to handle increased traffic.
        - Implement caching mechanisms like Redis to optimize response times.
    - Step 6: CI/CD for ML Models (MLOps)
        - Automate retraining and deployment with Tekton, GitHub Actions, or Jenkins.
        - Store model versions in MLflow or Model Registry for easy rollback.

4. What is model drift, and how do you handle it?
    - Model drift happens when a model`s performance degrades over time due to changes in real-world data.
    - Handle Model Drift
        - Continuous Monitoring: Track performance metrics using Prometheus, Grafana, or MLflow.
        - Periodic Retraining: Re-train the model with fresh data.
        - Adaptive Learning: Implement online learning techniques.
        - Drift Detection Tools: Use Evidently AI or River for detecting drift.

5. How would you optimize an ML model for inference speed and efficiency?
    - Quantization: Convert weights to lower precision (e.g., FP32 → INT8).
    - Pruning: Remove unnecessary model weights.
    - Batching: Process multiple inputs at once.
    - Use Efficient Model Architectures: Like MobileNet, EfficientNet for edge devices.
    - Leverage Hardware Acceleration: Run on TPUs, GPUs, or specialized inference engines.

6. How does transfer learning work in deep learning?
    - It uses a pre-trained model and fine-tunes it on a new dataset, reducing training time and data requirements.

7. What are hyperparameter tuning methods?
    - Grid Search, Random Search, Bayesian Optimization, and Hyperband.

8. How does Kubernetes help in ML model deployment?
    - Kubernetes provides scalability, auto-healing, and rolling updates, making it ideal for serving ML models in production.