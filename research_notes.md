# 合成数据研究笔记

## GANs理论基础

### 关键论文
1. **A Mathematical Introduction to Generative Adversarial Nets (GAN)**
   - 作者: Yang Wang
   - arXiv: 2009.00169
   - 链接: https://arxiv.org/abs/2009.00169
   - 摘要: 从数学角度提供GANs的概述,为数学专业学生提供更熟悉的语言介绍GANs
   - 关键点: 博弈论基础、纳什均衡、数学证明

2. **Do GANs always have Nash equilibria?**
   - 链接: http://proceedings.mlr.press/v119/farnia20a.html
   - 关键发现: GAN零和博弈可能没有纳什均衡
   - 意义: 解释了GAN训练不稳定的数学原因

3. **GANs trained by a two time-scale update rule converge to a local Nash equilibrium**
   - 关键贡献: 证明了TTUR在温和假设下收敛到局部纳什均衡
   - 引用次数: 20461次

## 需要深入研究的方向

### 01-理论基础
- GANs的博弈论基础
- VAEs的变分推断
- 扩散模型的随机微分方程
- 收敛性证明

### 02-核心方法
- 深度生成模型
- 统计方法
- 基于规则的方法

### 03-应用领域
- 计算机视觉
- 自然语言处理
- 时间序列
- 表格数据
