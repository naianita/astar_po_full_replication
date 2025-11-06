# A*-PO Full Replication

This repository contains the implementation of **A*-Policy Optimization (A*-PO)** for training LLMs on mathematical reasoning tasks, replicating the PAG (Policy as Generative Verifier) paper approach but using A*-PO instead of PPO.

## 🎯 Overview

- **Model**: Qwen2.5-1.5B-Instruct
- **Dataset**: MATH dataset (competition_math from HuggingFace)
- **Algorithm**: A*-PO (A* Policy Optimization)
- **Environment**: Optimized for Google Colab with T4 GPU (10GB memory constraint)


## 📊 Features

- **Memory Optimized**: Configured to use <10GB GPU memory
- **End-to-End**: Complete implementation from data loading to evaluation
- **A*-PO Algorithm**: Two-stage policy optimization:
  - Stage 1: Offline trajectory collection
  - Stage 2: Policy and value network updates
- **Reward Model**: Automatic correctness checking for mathematical solutions
- **Value Network**: MLP-based value estimator for advantage computation

## 🔧 Configuration

The notebook is configured with memory-safe defaults:
- Train dataset: 500 samples
- Eval dataset: 50 samples
- Max sequence length: 768 tokens
- Max new tokens: 128

Adjust these parameters in the notebook cells based on your GPU memory availability.

## 📚 References

- MATH Dataset: [Hendrycks et al.](https://github.com/hendrycks/math)
- Qwen Model: [Qwen2.5-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)


##Citation

@article{hendrycksmath2021,
  title={Measuring Mathematical Problem Solving With the MATH Dataset},
  author={Dan Hendrycks and Collin Burns and Saurav Kadavath and Akul Arora and Steven Basart and Eric Tang and Dawn Song and Jacob Steinhardt},
  journal={NeurIPS},
  year={2021}
}

@article{jiang2025pag,
  title={PAG: Multi-Turn Reinforced LLM Self-Correction with Policy as Generative Verifier},
  author={Jiang, Yuhua and Xiong, Yuwen and Yuan, Yufeng and Xin, Chao and Xu, Wenyuan and Yue, Yu and Zhao, Qianchuan and Yan, Lin},
  journal={arXiv preprint arXiv:2506.10406},
  year={2025}
}
