# 🧠 ML Experiments

Personal deep learning and reinforcement learning experimental repository.

This repo documents my hands-on exploration of various ML concepts: implementing models with PyTorch (CNN, VAE, GAN), experimenting with RL algorithms (Q-learning, DQN), and building simple game AI agents. It's a workspace for iterating on ideas and recording what I learned along the way.

---

## Table of Contents

- [Overview](#overview)
- [What's Inside](#whats-inside)
- [Quick Start](#quick-start)
- [Running Examples](#running-examples)
- [Experiment Workflow](#experiment-workflow)
- [Data & Models](#data--models)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This is my personal ML playground where I:
- Implement standard architectures (CNN, VAE, GAN, VGG) and custom variants from scratch
- Experiment with RL algorithms and test them on grid-world or game environments
- Build AI agents for simple games (Snake, Flappy Bird, Gomoku)
- Document findings and iterate on model design

The goal is learning by doing — not a production library, but a space to build intuition and test ideas quickly.

---

## What's Inside

```
MLExperiments/
├── pytorch/              # PyTorch model implementations and training scripts
│   ├── CGAN.py          # Conditional GAN for class-conditioned generation
│   ├── CNNet.py         # Basic CNN for image classification
│   ├── VAE.py           # Variational Autoencoder
│   ├── DiscoGAN.py      # Style transfer via DiscoGAN
│   ├── VGG.py           # VGG network variant
│   ├── Q-learning and SARSA.py  # Tabular RL on grid worlds
│   ├── download.py      # Dataset utilities and preprocessing
│   └── not_done/        # WIP experiments (e.g., incomplete DQN)
│
├── x-game/              # Simple game environments and AI agents
│   ├── ai-snake.py      # Snake AI using Q-learning
│   ├── ai-bird-dqn.py   # Flappy Bird AI (DQN variant)
│   ├── Gomoku.py        # Gomoku/Connect-5 game engine
│   └── two_player_pong.py  # Simple Pong game
│
├── models/              # Trained weights and checkpoints (in .gitignore)
├── reports/             # Experiment notes and findings
└── README.md
```

---

## Quick Start

### Prerequisites
- Python 3.8+
- Virtual environment (venv or conda recommended)

### Setup

1. Clone and enter the repo:
```bash
git clone https://github.com/maryon-zhao/MLExperiments.git
cd MLExperiments
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # macOS / Linux
venv\Scripts\activate     # Windows
```

3. Install dependencies:
```bash
pip install torch torchvision numpy matplotlib gym
```

For GPU support, follow [PyTorch's installation guide](https://pytorch.org/get-started/locally/) for your CUDA version.

---

## Running Examples

### Train a VAE
```bash
python pytorch/VAE.py --epochs 50 --batch_size 32 --lr 0.001
```

### Run Q-learning on a grid world
```bash
python pytorch/Q-learning\ and\ SARSA.py --mode train --episodes 1000
```

### Play Snake with AI agent
```bash
python x-game/ai-snake.py --render --episodes 100
```

See individual script headers for all available arguments and hyperparameter options.

---

## Experiment Workflow

**Typical flow for a new idea:**

1. Start in `pytorch/` or `x-game/` with a new `.py` file
2. Implement the model/algorithm + basic train/eval loop
3. Run locally to verify it works and collect results
4. Document findings in `reports/` (methods, results, next steps)
5. Keep clean `.py` files in the main directories; move incomplete work to `not_done/`

**Before sharing:**
- Test that the README instructions work in a fresh clone
- Verify at least one end-to-end example runs without errors
- Update hyperparameters and expected results in script headers

---

## Data & Models

- **Model weights** (`.pth`, `.pt`) are stored in `models/` and excluded from git via `.gitignore`
- **Large datasets** should also be in `.gitignore` — use download scripts in `pytorch/download.py` to fetch them at runtime
- Small example datasets or toy data can be committed if needed

To add your own model:
```bash
cp my_trained_model.pth models/
# Update the training script to save/load from models/
```

---

## Contributing

This is a personal learning repo, but you're welcome to:
1. Point out bugs or suggest improvements via Issues
2. Fork and experiment with your own variations
3. Share RL environment ideas or cool model architectures

---

## License

MIT License — feel free to use and adapt for your own projects.

---

## Questions?

Open an issue or reach out if you want to discuss an experiment, extend an idea, or have questions about the implementations.

Happy experimenting! 🚀
