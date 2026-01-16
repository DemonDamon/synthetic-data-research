# Researches - 合成数据研究资源库

本目录包含合成数据生成领域的系统化研究资源,从理论基础到工业实践,为研究者和从业者提供全方位的知识体系。

## 目录结构

### [01-理论基础 (Theoretical Foundations)](./01-theoretical-foundations/)
深入探讨主流生成模型的数学原理、收敛性证明和理论分析。

**子主题**:
- **GANs** - 博弈论基础、纳什均衡、训练稳定性
- **VAEs** - 变分推断、ELBO推导、重参数化技巧
- **Diffusion Models** - 随机微分方程、分数匹配、去噪过程
- **Other Methods** - SMOTE、物理仿真、统计方法

### [02-核心方法 (Core Methods)](./02-core-methods/)
系统梳理合成数据生成的核心方法论和技术路线。

**子主题**:
- **深度生成模型** - 神经网络架构、训练策略
- **统计方法** - 核密度估计、高斯混合模型
- **基于规则的方法** - 程序化生成、模板方法

### [03-应用领域 (Application Domains)](./03-application-domains/)
探索合成数据在不同领域的应用案例和最佳实践。

**子主题**:
- **计算机视觉** - 图像生成、目标检测、语义分割
- **自然语言处理** - 文本生成、数据增强、对话系统
- **时间序列** - 金融数据、传感器数据、医疗信号
- **表格数据** - 结构化数据生成、隐私保护数据共享

### [04-关键技术 (Key Technologies)](./04-key-technologies/)
深入研究合成数据生成中的关键技术和方法论。

**子主题**:
- **隐私保护** - 差分隐私、联邦学习、安全多方计算
- **小样本学习** - Few-shot生成、数据增强策略
- **域随机化** - Sim2Real、迁移学习
- **可控生成** - 条件生成、属性控制

### [05-质量评估 (Quality Evaluation)](./05-quality-evaluation/)
建立合成数据质量评估的理论框架和实践方法。

**子主题**:
- **保真度评估** - 统计相似性、分布距离
- **多样性评估** - 覆盖率、模式检测
- **实用性评估** - 下游任务性能、TSTR/TRTR
- **隐私性评估** - 成员推断攻击、隐私泄露检测

### [06-前沿趋势 (Emerging Trends)](./06-emerging-trends/)
追踪合成数据生成领域的最新研究进展和未来方向。

**子主题**:
- **LLMs与合成数据** - 大语言模型生成、自举学习
- **世界模型** - 物理AI、环境模拟
- **跨模态生成** - 文本到图像/视频/3D、多模态融合

### [07-伦理与风险 (Ethics and Risks)](./07-ethics-and-risks/)
分析合成数据带来的伦理挑战和潜在风险。

**子主题**:
- **偏见问题** - 偏见继承与放大、公平性
- **数据完整性** - 误用风险、学术诚信
- **缓解策略** - 去偏方法、伦理准则

### [08-工业实践 (Industry Practices)](./08-industry-practices/)
总结工业界在合成数据领域的实践经验和工具平台。

**子主题**:
- **NVIDIA案例** - Omniverse、Isaac Sim、Nemotron
- **开源工具** - Synthetic Data Vault、Gretel、CTGAN
- **最佳实践** - 工程化方案、部署策略

### [09-学术资源 (Academic Resources)](./09-academic-resources/)
汇总学术论文、数据集、基准测试等研究资源。

**子主题**:
- **论文列表** - 按主题分类的重要论文
- **数据集** - 公开数据集、基准数据集
- **基准测试** - 评估标准、排行榜

## 使用指南

### 初学者路径

**第一阶段: 理论基础** (1-2周)
1. 从[理论基础](./01-theoretical-foundations/)开始,理解GANs、VAEs、Diffusion Models的基本原理
2. 重点关注每个模型的核心思想和训练目标
3. 不必深究复杂的数学推导,先建立整体认知

**第二阶段: 应用实践** (2-3周)
1. 选择感兴趣的[应用领域](./03-application-domains/),如计算机视觉或NLP
2. 学习该领域的典型应用案例
3. 尝试运行开源代码,理解实际应用流程

**第三阶段: 质量评估** (1周)
1. 学习[质量评估](./05-quality-evaluation/)方法
2. 理解如何评估生成数据的好坏
3. 掌握常用评估指标(FID、IS、TSTR等)

**第四阶段: 前沿探索** (持续)
1. 关注[前沿趋势](./06-emerging-trends/)
2. 了解最新研究进展
3. 思考未来发展方向

### 研究者路径

**深度理论研究**:
1. 精读[理论基础](./01-theoretical-foundations/)中的数学推导
2. 查阅原始论文,理解证明过程
3. 探索理论改进方向

**方法创新**:
1. 研究[核心方法](./02-core-methods/)的优缺点
2. 结合[关键技术](./04-key-technologies/)探索新方法
3. 在[质量评估](./05-quality-evaluation/)框架下验证创新

**应用落地**:
1. 选择具体[应用领域](./03-application-domains/)
2. 参考[工业实践](./08-industry-practices/)的经验
3. 关注[伦理与风险](./07-ethics-and-risks/)

### 工程师路径

**快速上手**:
1. 浏览[理论基础](./01-theoretical-foundations/)了解基本概念
2. 直接进入[工业实践](./08-industry-practices/)学习工具使用
3. 参考[应用领域](./03-application-domains/)的案例

**工程优化**:
1. 学习[核心方法](./02-core-methods/)的实现细节
2. 掌握[关键技术](./04-key-technologies/)如域随机化
3. 建立[质量评估](./05-quality-evaluation/)流程

**生产部署**:
1. 研究[工业实践](./08-industry-practices/)的最佳实践
2. 考虑[伦理与风险](./07-ethics-and-risks/)的缓解策略
3. 持续关注[前沿趋势](./06-emerging-trends/)

## 文档规范

每个子目录遵循统一的结构:

```
主题目录/
├── README.md           # 主题概览和导航
├── 子主题1/
│   ├── README.md       # 子主题总结
│   ├── detailed_report.md  # 深度研究报告
│   ├── technical_notes.md  # 技术笔记
│   ├── case_studies.md     # 案例研究
│   └── images/         # 图片资源
├── 子主题2/
│   └── ...
└── 子主题3/
    └── ...
```

## 贡献指南

欢迎贡献新的研究内容、案例分析或工具推荐:

1. **内容贡献**: 补充新的研究报告、技术笔记
2. **案例分享**: 分享实践经验和应用案例
3. **资源推荐**: 推荐优质论文、工具、数据集
4. **错误修正**: 指出文档中的错误或不准确之处

## 更新日志

- **2026-01-16**: 初始版本发布
  - 完成理论基础部分(GANs、VAEs、Diffusion Models)
  - 建立目录结构和文档规范
  - 整合用户提供的研究报告

## 参考资源

### 综合性资源
- **Papers with Code** - 最新论文和代码实现
- **arXiv** - 预印本论文库
- **GitHub** - 开源项目和工具

### 会议与期刊
- **NeurIPS, ICML, ICLR** - 机器学习顶会
- **CVPR, ICCV, ECCV** - 计算机视觉顶会
- **ACL, EMNLP** - 自然语言处理顶会

### 在线课程
- **Stanford CS236** - Deep Generative Models
- **MIT 6.S191** - Introduction to Deep Learning
- **Fast.ai** - Practical Deep Learning

### 技术博客
- **Lil'Log** - 深度学习理论解析
- **The AI Summer** - AI技术深度文章
- **Distill.pub** - 可视化机器学习

---

**维护者**: Synthetic Data Research Community  
**最后更新**: 2026-01-16
