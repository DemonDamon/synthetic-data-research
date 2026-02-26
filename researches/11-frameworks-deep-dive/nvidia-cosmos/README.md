# NVIDIA Cosmos生态系统深度调研

## GitHub组织概览

**GitHub地址**: https://github.com/nvidia-cosmos  
**官网**: https://www.nvidia.com/en-us/ai/cosmos/  
**联系邮箱**: mharrim@nvidia.com  
**关注者**: 1.7k followers  
**许可证**: Apache-2.0

## 核心定位

NVIDIA Cosmos™是一个专为物理AI构建的平台,具备最先进的生成式世界基础模型(WFMs)、强大的防护机制和加速的数据处理与管理流水线。专为真实世界系统设计,使开发者能够快速推进物理AI应用,如自动驾驶汽车(AVs)、机器人和视频分析AI代理。

## 三大核心模型类型

### 1. Cosmos-Predict (世界生成)
- **类型**: World Generation
- **功能**: 根据初始帧预测新的未来帧
- **用例**: 数据生成 & 策略评估
- **输入**: 文本、图像、视频
- **输出**: 视频

### 2. Cosmos-Transfer (多控制网络)
- **类型**: Multi-Controlnet
- **功能**: 将现有控制帧转换为视频片段中的逼真帧
- **用例**: 数据增强
- **输入**: 多种视频模态(RGB、深度、分割等)
- **输出**: 视频

### 3. Cosmos-Reason (推理VLM)
- **类型**: Reasoning VLM (视觉语言模型)
- **功能**: 对视频片段中的帧进行推理
- **用例**: 数据管理、机器人规划和策略 & 视觉AI代理
- **输入**: 视频、图像 & 文本
- **输出**: 文本

## GitHub仓库列表(13个)

### 核心模型仓库

#### 1. cosmos-predict2.5 ⭐840
- **描述**: Cosmos World Foundation Models (WFMs)家族的最新版本,专门用于以视频形式模拟和预测世界的未来状态
- **语言**: Python
- **Stars**: 840 | Forks: 91
- **链接**: https://github.com/nvidia-cosmos/cosmos-predict2.5

#### 2. cosmos-transfer2.5 ⭐473
- **描述**: 基于Cosmos-Predict2.5构建,根据多个空间控制输入生成高质量的世界模拟
- **语言**: Python
- **Stars**: 473 | Forks: 72
- **链接**: https://github.com/nvidia-cosmos/cosmos-transfer2.5

#### 3. cosmos-reason2 ⭐254
- **描述**: 理解物理常识并通过长链思维推理过程以自然语言生成适当的具身决策
- **语言**: Python
- **Stars**: 254 | Forks: 50
- **链接**: https://github.com/nvidia-cosmos/cosmos-reason2

### 工具和框架仓库

#### 4. cosmos-cookbook ⭐282
- **描述**: NVIDIA Cosmos生态系统的后训练脚本和样本
- **语言**: Python
- **Stars**: 282 | Forks: 67
- **链接**: https://github.com/nvidia-cosmos/cosmos-cookbook

#### 5. cosmos-rl ⭐340
- **描述**: 专为物理AI应用设计的灵活且可扩展的强化学习框架
- **语言**: Python
- **Stars**: 340 | Forks: 49
- **链接**: https://github.com/nvidia-cosmos/cosmos-rl

#### 6. cosmos-curate ⭐153
- **描述**: 强大的视频管理系统,使用先进的AI模型和分布式计算处理、分析和组织视频内容
- **语言**: Python
- **Stars**: 153 | Forks: 26
- **链接**: https://github.com/nvidia-cosmos/cosmos-curate

#### 7. cosmos-dependencies ⭐8
- **描述**: 依赖管理
- **语言**: Shell
- **Stars**: 8 | Forks: 5
- **链接**: https://github.com/nvidia-cosmos/cosmos-dependencies

### 早期版本仓库

#### 8. cosmos-predict1 ⭐414
- **描述**: 通用世界基础模型集合,可微调为下游应用的定制世界模型
- **语言**: Jupyter Notebook
- **Stars**: 414 | Forks: 78
- **链接**: https://github.com/nvidia-cosmos/cosmos-predict1

#### 9. cosmos-transfer1 ⭐778
- **描述**: 世界到世界的转换模型,旨在弥合模拟和真实世界环境之间的感知鸿沟
- **语言**: Python
- **Stars**: 778 | Forks: 102
- **链接**: https://github.com/nvidia-cosmos/cosmos-transfer1

#### 10. cosmos-reason1 ⭐919
- **描述**: 理解物理常识并以自然语言生成适当的具身决策
- **语言**: Python
- **Stars**: 919 | Forks: 81
- **链接**: https://github.com/nvidia-cosmos/cosmos-reason1

## Cosmos Cookbook

Cosmos Cookbook为开发者提供分步配方和后训练脚本,以快速构建、定制和部署NVIDIA的Cosmos世界基础模型,用于机器人和自主系统。

## 物理AI开发中的用例

世界基础模型专为加速改进下游模型任务在各个阶段的性能而构建,如飞轮图所示。

## 技术特点

1. **全部可定制**: 三种模型类型都可以在后训练中进行定制
2. **开源**: 所有仓库均采用Apache-2.0许可证
3. **活跃社区**: 1.7k关注者,活跃的Discussions
4. **完整生态**: 从模型到工具到数据管理的完整链条

## 主要编程语言

- Python (主要)
- Shell
- Jupyter Notebook

## 热门主题标签

- video-generation
- world-models

---

**调研时间**: 2026年2月26日


## 官方文档详细信息

**文档地址**: https://docs.nvidia.com/cosmos/latest/introduction.html  
**当前版本**: 2.2.0

### Cosmos平台架构

NVIDIA Cosmos是一个**开发者优先(developer-first)**的平台,用于设计物理AI系统。平台分为多个组件,每个组件都有自己的GitHub仓库。

### 各版本详细说明

#### Cosmos-Predict系列

**Cosmos-Predict2.5** (最新版本)
- 基于流(flow-based)的模型,专门用于以视频形式模拟和预测世界的未来状态
- **统一模型**: 将Text2World、Image2World和Video2World统一到单个模型中
- **文本编码器**: 使用Cosmos-Reason1作为文本编码器(物理AI推理视觉语言模型VLM)
- **显著改进**: 在质量和提示对齐方面显著优于Cosmos-Predict1

**Cosmos-Predict2**
- Cosmos World Foundation Models (WFMs)生态系统的关键分支
- 专注于通过先进的世界建模进行未来状态预测
- **两大能力**:
  1. 文本到图像生成: 从文本描述创建高质量图像
  2. 视频到世界生成: 从视频输入生成视觉模拟

**Cosmos-Predict1**
- 通用世界基础模型(WFMs)集合,用于推理
- 提供后训练脚本,用于特定物理AI用例的模型定制

#### Cosmos-Transfer系列

**Cosmos-Transfer2.5** (最新版本)
- **多控制网络(multi-controlnet)**: 接受多种视频模态的结构化输入,包括RGB、深度、分割等
- **JSON配置**: 用户可以使用基于JSON的controlnet_specs配置生成
- **灵活推理**: 只需几个命令即可运行推理
- **多GPU支持**: 支持单视频推理、自动控制图生成和多GPU设置

**Cosmos-Transfer1**
- 预训练的、基于扩散的条件世界模型集合
- 设计用于多模态、可控的世界生成
- **多模态控制**: 基于多个空间控制输入创建世界模拟,涵盖分割、深度、边缘图等模态
- **灵活权重**: 可以在不同空间位置和时间实例对不同条件输入进行不同权重设置
- **高度可定制**: 实现高度可定制的世界生成
- **Sim2Real应用**: 特别适用于各种世界到世界的转换应用,包括Sim2Real

#### Cosmos-Reason系列

**Cosmos-Reason2** (下一代)
新功能包括:
1. **增强的物理AI推理**: 改进的时空理解和时间戳精度
2. **目标检测**: 2D/3D点定位和边界框坐标,以及推理解释和标签
3. **长上下文理解**: 支持高达256K输入token

**Cosmos-Reason1**
- **开放、可定制**: 用于物理AI和机器人的推理视觉语言模型(VLM)
- **类人推理**: 使机器人和视觉AI代理能够像人类一样推理
- **先验知识**: 使用先验知识、物理理解和常识来理解和行动于真实世界
- **时空理解**: 理解空间、时间和基础物理
- **规划模型**: 可以作为规划模型推理具身代理可能采取的下一步行动
- **长尾场景**: 擅长导航具有时空理解的多样化物理世界场景的长尾
- **后训练**: 使用物理常识和具身推理数据进行后训练,包括监督微调和强化学习
- **链式思维**: 使用链式思维(chain-of-thought)推理能力理解世界动态,无需人工标注

### 技术优势总结

1. **统一架构**: Predict2.5将多种生成任务统一到单个模型
2. **多模态支持**: Transfer系列支持RGB、深度、分割等多种模态
3. **推理能力**: Reason系列提供类人推理和物理常识理解
4. **可定制性**: 所有模型都支持后训练定制
5. **Sim2Real**: Transfer系列专门优化了从仿真到真实的迁移
6. **长上下文**: Reason2支持高达256K token的长上下文理解
7. **开源生态**: 完全开源,开发者可以自由访问和定制

### 文档结构

- Introduction (简介)
- Release Notes (发布说明)
- Prerequisites (先决条件)
- NVIDIA NIMs for Cosmos (NVIDIA推理微服务)
- 各模型详细文档 (Predict2.5, Predict2, Predict1, Transfer2.5, Transfer1, Reason2, Reason1)
- Frequently Asked Questions (常见问题)
- Feedback and Support (反馈和支持)
- Cosmos Guardrail (防护机制)
- License (许可证)

---

**文档更新时间**: 2026年2月26日
