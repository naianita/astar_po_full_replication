# A*-PO Full Replication

This repository contains the implementation of **A*-Policy Optimization (A*-PO)** for training LLMs on mathematical reasoning tasks, replicating the PAG (Policy as Generative Verifier) paper approach but using A*-PO instead of PPO.

## 🎯 Overview

- **Model**: Qwen2.5-1.5B-Instruct
- **Dataset**: MATH dataset (competition_math from HuggingFace)
- **Algorithm**: A*-PO (A* Policy Optimization)
- **Environment**: Optimized for Google Colab with T4 GPU (10GB memory constraint)

## 📁 Files

- `pag_astar_po_colab (1).ipynb` - Complete implementation notebook for Google Colab

## 🚀 Quick Start

1. Open the notebook in Google Colab
2. Enable GPU: Runtime → Change runtime type → GPU (T4)
3. Run all cells
4. Training will take approximately 2-3 hours

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

- PAG Paper: Policy as Generative Verifier
- MATH Dataset: [Hendrycks et al.](https://github.com/hendrycks/math)
- Qwen Model: [Qwen2.5-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)

## ⚠️ Note on Out of Memory Errors

If you encounter OOM errors, see the memory optimization settings in the notebook:
- Reduce `train_size` and `max_prompts`
- Decrease `max_new_tokens` and sequence lengths
- Process fewer trajectories per epoch

## 📝 License

See repository license file for details.