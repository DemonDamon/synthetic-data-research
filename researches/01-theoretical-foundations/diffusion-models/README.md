# 扩散模型 (Diffusion Models) 理论基础

## 概述

本目录全面阐述扩散模型(Diffusion Models)的理论基础,从非平衡热力学、随机过程和分数匹配的角度深入分析扩散模型的数学原理。扩散模型是当前最先进的生成模型,在图像、音频、视频生成等领域取得了突破性成果。

## 文档列表

- **[详细研究报告](./detailed_report.md)** - 扩散模型理论基础的完整论述,包括前向扩散、反向去噪、分数匹配、随机微分方程视角以及采样方法

## 核心概念

### 前向扩散过程

前向过程通过马尔可夫链逐步向数据添加高斯噪声:

```
q(x_t | x_{t-1}) = N(x_t; √(1-β_t) x_{t-1}, β_t I)
```

经过T步后,数据x_0被转化为纯噪声x_T ~ N(0,I)。

**关键性质**: 可以直接从x_0采样任意时间步的x_t:

```
x_t = √(ᾱ_t) x_0 + √(1-ᾱ_t) ε,  其中 ε ~ N(0,I)
```

这使得训练过程非常高效。

### 反向去噪过程

反向过程学习如何从噪声中逐步恢复数据:

```
p_θ(x_{t-1} | x_t) = N(x_{t-1}; μ_θ(x_t,t), Σ_θ(x_t,t))
```

**核心参数化**: 不直接预测均值,而是预测添加的噪声ε:

```
μ_θ(x_t,t) = 1/√(α_t) (x_t - β_t/√(1-ᾱ_t) ε_θ(x_t,t))
```

### 训练目标

简化的训练目标非常直观:

```
L_simple = E_{t,x_0,ε}[||ε - ε_θ(x_t,t)||²]
```

训练神经网络预测添加到数据的噪声。

## 理论视角

### 变分推断视角

扩散模型可以从变分推断角度理解,优化证据下界(ELBO):

```
-log p_θ(x_0) ≤ E_q[log q(x_{1:T}|x_0)/p_θ(x_{0:T})]
```

ELBO可以分解为多个KL散度项的和。

### 分数匹配视角

扩散模型与去噪分数匹配(Denoising Score Matching)有深刻联系。

**分数函数**: 数据分布对数概率密度的梯度

```
s(x) = ∇_x log p(x)
```

**联系**: 噪声预测网络与分数函数的关系

```
s_θ(x_t,t) = -ε_θ(x_t,t) / √(1-ᾱ_t)
```

训练扩散模型等价于在多个噪声水平上进行去噪分数匹配。

### 随机微分方程视角

Song等人将离散时间扩散推广到连续时间,使用SDE描述:

**前向SDE**:
```
dx = f(x,t)dt + g(t)dw
```

**反向SDE** (Anderson定理):
```
dx = [f(x,t) - g²(t)∇_x log p_t(x)]dt + g(t)dw̄
```

**概率流ODE** (确定性采样):
```
dx = [f(x,t) - 1/2 g²(t)∇_x log p_t(x)]dt
```

这个统一框架连接了不同的扩散模型变体。

## 采样方法

### DDPM采样

标准迭代去噪过程:

```
x_{t-1} = 1/√(α_t) (x_t - β_t/√(1-ᾱ_t) ε_θ(x_t,t)) + √(β_t) z
```

需要1000步左右,速度较慢。

### DDIM采样

确定性快速采样:

```
x_{t-1} = √(ᾱ_{t-1}) pred_x_0 + √(1-ᾱ_{t-1}) ε_θ(x_t,t)
```

可以在10-50步内生成高质量样本。

### DPM-Solver

使用高阶数值求解器加速ODE求解,进一步减少采样步数。

### Latent Diffusion

在VAE的潜在空间中进行扩散,大幅降低计算成本:
- Stable Diffusion使用这一策略
- 在低维潜在空间中扩散更高效

## 理论优势

### 训练稳定性

扩散模型训练过程极其稳定,目标函数明确,不需要对抗训练。

### 生成质量

在图像生成任务中达到或超越GANs,FID分数创新低。

### 多样性

采样过程的随机性自然保证了生成样本的多样性,避免模式崩溃。

### 理论完备性

多个理论视角(变分推断、分数匹配、SDE)相互印证,提供深刻理解。

### 可扩展性

易于扩展到条件生成、跨模态生成、逆问题求解等多种任务。

## 主要挑战

### 采样速度

主要缺点是采样慢,需要多次迭代。虽然有加速方法,但仍比GANs慢。

### 计算成本

训练大规模扩散模型需要大量计算资源,尤其是高分辨率生成。

### 似然计算

虽然可以通过ODE计算精确似然,但计算成本很高。

## 改进方向

### 加速采样

**一致性模型** (Consistency Models): 直接学习从任意时间步到数据的映射,实现单步生成。

**蒸馏方法**: 将多步扩散模型蒸馏为少步模型。

**自适应步长**: 根据噪声水平动态调整采样步长。

### 架构改进

**U-Net改进**: 引入注意力机制、残差连接、组归一化等。

**Transformer架构**: 使用Transformer替代U-Net,如DiT (Diffusion Transformer)。

**条件机制**: 改进条件信息的注入方式,如Classifier-free Guidance。

### 应用扩展

**条件生成**: 文本到图像(Stable Diffusion, DALL-E 2)、图像修复、超分辨率。

**跨模态生成**: 文本到视频、文本到3D、音频生成。

**逆问题求解**: 图像去噪、去模糊、压缩感知、医学成像重建。

## 关键文献

1. **Ho et al. (2020)** - Denoising Diffusion Probabilistic Models (DDPM, 引用33135次)
2. **Song & Ermon (2019)** - Generative Modeling by Estimating Gradients
3. **Song et al. (2021)** - Score-Based Generative Modeling through SDEs
4. **Song et al. (2021)** - Denoising Diffusion Implicit Models (DDIM)
5. **Huang et al. (2021)** - A Variational Perspective on Diffusion Models
6. **Lu et al. (2022)** - DPM-Solver (快速采样)
7. **Rombach et al. (2022)** - Latent Diffusion Models (Stable Diffusion)
8. **Song et al. (2023)** - Consistency Models (单步生成)

## 学习资源

**推荐阅读顺序**:
1. DDPM论文理解基本框架
2. Score-based模型理解分数匹配
3. SDE论文理解连续时间视角
4. DDIM论文学习快速采样
5. Latent Diffusion理解高效实现

**在线资源**:
- "What are Diffusion Models?" (Lil'Log博客)
- "How diffusion models work" (The AI Summer)
- Hugging Face Diffusers库文档
- Stable Diffusion论文和代码

**视频教程**:
- Yang Song的扩散模型讲座
- Sohl-Dickstein的DDPM讲解
- Stable Diffusion技术解析

## 实践建议

### 训练技巧

**噪声调度选择**:
- 线性调度适合简单数据
- 余弦调度适合复杂图像
- 可学习调度用于特定任务

**时间步采样**:
- 均匀采样所有时间步
- 重要性采样关键时间步
- 课程学习从简单到困难

**架构设计**:
- U-Net用于图像
- Transformer用于序列和高分辨率
- 多尺度架构处理不同细节

### 评估方法

**生成质量**:
- FID (Fréchet Inception Distance)
- IS (Inception Score)
- Precision & Recall

**采样效率**:
- 达到目标质量所需步数
- 每步计算时间
- 总生成时间

## 最新进展

**2023-2026年重要进展**:
- Consistency Models实现单步生成
- DiT将Transformer引入扩散模型
- Stable Diffusion 3提升文本理解
- Video Diffusion实现高质量视频生成
- 3D Diffusion用于3D内容创作

## 图片资源

`images/` 文件夹包含:
- 前向扩散过程可视化
- 反向去噪过程可视化
- 分数函数示意图
- SDE与ODE对比
- 不同采样方法的对比
- 噪声调度可视化

---

**相关目录**:
- [GANs理论基础](../gans/)
- [VAEs理论基础](../vaes/)
- [应用案例](../../03-application-domains/)
- [前沿趋势](../../06-emerging-trends/)
