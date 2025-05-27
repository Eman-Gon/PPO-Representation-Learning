# PPO with Representation Learning

This project explores how dimensionality reduction techniques—specifically PCA and autoencoders—affect the performance of Proximal Policy Optimization (PPO) agents in reinforcement learning. The goal is to determine whether reducing the dimensionality of input observations can improve training efficiency, stability, and overall performance in continuous control environments.

## Motivation

Reinforcement learning environments like Walker2D or Ant generate high-dimensional state spaces due to complex robotic dynamics. These high-dimensional observations can slow down training and make it harder for agents to learn stable policies. We aim to apply representation learning techniques to compress these observations and evaluate their impact on the training process.

## Methods

We evaluate three setups:
1. **Baseline**: PPO agent trained using raw state inputs.
2. **PCA**: PPO agent trained using PCA-compressed inputs.
3. **Autoencoder**: PPO agent trained using inputs compressed by a trained autoencoder.

All agents are implemented using Stable-Baselines3 and tested initially on the `CartPole-v1` environment. The pipeline will later be extended to more complex environments like `Walker2D` from the Gymnasium suite.

## Files

- `PPO_with_Compressed_Observations-2.ipynb`: Main Colab notebook containing training code, logging, and performance comparisons.
- `autoencoder_model.py`: Python script with autoencoder architecture and training logic.
- Additional `.py` files may include PCA wrappers and preprocessing utilities.

## Evaluation Metrics

- **Total Reward**: Final and average episode reward during training.
- **Convergence Speed**: How quickly each agent reaches a stable policy.
- **Explained Variance**: For PCA-based inputs.
- **Reconstruction Error**: For autoencoder-based inputs.
- **Training Time**: To assess computational efficiency.
- **Qualitative Behavior**: Whether the agent still performs the task correctly.

## Timeline

- **Week 4–5**: Baseline PPO on CartPole and Walker2D using raw inputs.
- **Week 6–7**: Implement PCA and autoencoder feature reduction.
- **Week 8–9**: Train agents using compressed inputs and compare performance.
- **Week 10**: Final analysis, report writing, and presentation.

## Future Work

- Extend experiments to vision-based environments.
- Explore other compression methods such as VAEs or contrastive learning.
- Use learned features for auxiliary tasks like reward shaping or transfer learning.

## References

- Schulman et al., "Proximal Policy Optimization Algorithms", arXiv:1707.06347
- Gymnasium Documentation: https://gymnasium.farama.org
- skrl Documentation: https://skrl.readthedocs.io
- Hugging Face Deep RL Course: https://huggingface.co/learn/deep-rl-course
- ALE (Arcade Learning Environment): https://ale.farama.org
