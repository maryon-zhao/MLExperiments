# 🧠 我的机器学习实验仓库

个人深度学习和强化学习的实验项目。

这个仓库记录了我对各种ML概念的动手实践：用PyTorch实现CNN、VAE、GAN等模型，探索强化学习算法（Q-learning、DQN），以及为一些简单游戏构建AI智能体。这是我学习ML的个人工作空间，通过做项目来深化理解和测试想法。

---

## 目录

- [项目简介](#项目简介)
- [仓库结构](#仓库结构)
- [快速开始](#快速开始)
- [运行示例](#运行示例)
- [实验工作流](#实验工作流)
- [数据与模型](#数据与模型)
- [贡献](#贡献)
- [许可证](#许可证)

---

## 项目简介

这是我的ML实验室，我在这里：
- 从零开始实现标准深度学习架构（CNN、VAE、GAN、VGG）以及自定义变种
- 在网格世界或游戏环境中测试强化学习算法
- 为简单游戏构建AI智能体（贪吃蛇、Flappy Bird、五子棋）
- 记录实验发现并迭代改进模型设计

目标是通过实践来学习——这不是一个生产级库，而是一个快速构建直觉和测试想法的学习空间。

---

## 仓库结构

```
MLExperiments/
├── pytorch/              # PyTorch 模型实现和训练脚本
│   ├── VAE.py           # 变分自编码器（主展示）
│   ├── CGAN.py          # 条件生成对抗网络
│   ├── CNNet.py         # 基础卷积神经网络
│   ├── DiscoGAN.py      # 图像风格迁移
│   ├── VGG.py           # VGG 网络实现
│   ├── Q-learning and SARSA.py  # 强化学习基础算法
│   ├── download.py      # 数据集下载和预处理工具
│   └── not_done/        # 未完成的实验
│
├── x-game/              # 游戏环境和 AI 智能体
│   ├── ai-snake.py      # 贪吃蛇 AI（主展示）
│   ├── Gomoku-MCTS.py   # 五子棋 + 蒙特卡洛树搜索（主展示）
│   ├── ai-bird-DQN-LR-pro1.py   # Flappy Bird AI
│   └── Gomoku.py        # 五子棋游戏引擎
│
├── models/              # 训练好的模型权重（已加入 .gitignore）
├── reports/             # 实验笔记和发现
└── README.md
```

---

## 快速开始

### 环境要求
- Python 3.8+
- 虚拟环境（推荐使用 venv 或 conda）

### 安装步骤

1. 克隆仓库：
```bash
git clone https://github.com/maryon-zhao/MLExperiments.git
cd MLExperiments
```

2. 创建并激活虚拟环境：
```bash
python -m venv venv
source venv/bin/activate  # macOS / Linux
venv\Scripts\activate     # Windows
```

3. 安装依赖：
```bash
pip install torch torchvision numpy matplotlib pygame gym
```

**GPU支持：** 如果需要用GPU加速训练，请按照 [PyTorch官方指南](https://pytorch.org/get-started/locally/) 安装对应CUDA版本的PyTorch。

---

## 运行示例

### 1. 训练变分自编码器（VAE）
```bash
python pytorch/VAE.py
```
- **说明**：在MNIST数据集上训练VAE，自动下载数据，每轮会保存重建图像到 `vae_samples/` 目录
- **依赖**：PyTorch、torchvision
- **预期**：~2分钟完成10轮训练，输出重建效果的可视化图像

### 2. 贪吃蛇AI游戏
```bash
python x-game/ai-snake.py
```
- **说明**：训练或加载已训练的DQN模型控制贪吃蛇
- **命令提示**：运行后会提示输入 `train`（训练）或 `play`（游玩）
- **依赖**：PyTorch、pygame、numpy
- **预期**：train模式下持续学习，play模式可看到AI玩游戏

### 3. 五子棋AI（蒙特卡洛树搜索）
```bash
python x-game/Gomoku-MCTS.py
```
- **说明**：用蒙特卡洛树搜索（MCTS）算法实现五子棋AI，可与AI对战
- **依赖**：Python标准库（无额外依赖）
- **预期**：启动交互式游戏，输入坐标与AI对战

---

## 实验工作流

**新想法的典型流程：**

1. 在 `pytorch/` 或 `x-game/` 创建新的 `.py` 文件
2. 实现模型/算法 + 基础训练/评估循环
3. 本地运行验证功能，收集结果
4. 将发现记录到 `reports/` 目录（方法、结果、后续方向）
5. 保持主目录整洁，把未完成的工作移到 `not_done/` 或创建 `archive/` 目录

**在分享前必做的事：**
- 在干净的clone环境中测试README的步骤是否有效
- 验证至少一个端到端的例子能成功运行
- 在脚本顶部更新超参和预期结果说明

---

## 数据与模型

- **模型权重**（`.pth`, `.pt`）存放在 `models/` 目录，已通过 `.gitignore` 排除
- **大型数据集**也应该加入 `.gitignore`——使用 `pytorch/download.py` 中的脚本在运行时自动下载
- 小型示例数据或玩具数据可以提交到仓库

添加自己的模型：
```bash
# 训练完成后保存模型
cp my_trained_model.pth models/

# 更新训练脚本以支持从 models/ 加载预训练权重
```

---

## 贡献

这是我的个人学习仓库，但欢迎你：
1. 通过 Issues 指出bug或改进建议
2. Fork后尝试自己的变种和优化
3. 分享有趣的RL环境想法或酷炫的模型架构

---

## 许可证

MIT 许可证 — 自由使用和改进。

---

## 有问题？

欢迎开Issue讨论某个实验、扩展想法或询问实现细节。

祝你实验愉快！🚀
