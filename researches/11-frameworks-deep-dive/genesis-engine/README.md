# Genesis物理引擎深度调研

## 项目概览

**官网**: https://genesis-embodied-ai.github.io/  
**GitHub**: https://github.com/Genesis-Embodied-AI/Genesis  
**文档**: https://genesis-world.readthedocs.io/  
**社区**: Discord, Wechat  
**论文**: Coming Soon

## 核心定位

Genesis是一个综合性物理仿真平台,专为通用机器人、具身AI和物理AI应用而设计。它同时是多个系统的集合体。

## 四大核心能力

### 1. 通用物理引擎
从底层重新构建的通用物理引擎,能够模拟广泛的材料和物理现象。

**特点**:
- 从零开始重新设计和构建
- 集成多种物理求解器及其耦合到统一框架中
- 支持多种材料和物理现象的模拟

### 2. 机器人仿真平台
轻量级、超快速、Pythonic且用户友好的机器人仿真平台。

**特点**:
- 轻量级架构
- 超高速性能
- Python友好的API
- 用户友好的设计

### 3. 照片级真实感渲染系统
强大且快速的照片级真实感渲染系统。

**特点**:
- 照片级真实感
- 高性能渲染
- 集成到仿真流程中

### 4. 生成数据引擎
将用户提示的自然语言描述转换为各种模态数据的生成数据引擎。

**特点**:
- 自然语言输入
- 多模态数据输出
- 自动化数据生成

## 生成框架的数据模态

Genesis的生成框架旨在自动生成以下模态的数据:

1. **物理准确且空间一致的视频** (Physically-accurate & spatially consistent videos)
2. **相机运动和参数** (Camera motion & parameters)
3. **人类和动物角色运动** (Human and animal character motion)
4. **机器人操作和运动策略,可部署到真实世界** (Robotic manipulation & locomotion policy, deployable to real-world)
5. **完全交互式3D场景** (Fully interactive 3D scene)
6. **开放世界关节对象生成** (Open-world articulated object generation)
7. **语音音频、面部动画和情感** (Speech audio, facial animation & emotion)

## 开源状态

**当前开源**:
- 底层物理引擎
- 仿真平台

**未来开源**:
- 生成框架将在不久的将来逐步开放

## 核心贡献者

Genesis由全球顶尖AI高校的华人团队主导开发,核心贡献者来自:

### 学术机构(20所)
1. Carnegie Mellon University (卡内基梅隆大学)
2. University of Maryland (马里兰大学)
3. Columbia University (哥伦比亚大学)
4. Stanford University (斯坦福大学)
5. MIT (麻省理工学院)
6. NVIDIA
7. University of Massachusetts Amherst (马萨诸塞大学阿默斯特分校)
8. Liquid AI
9. Peking University (北京大学)
10. Tsinghua University (清华大学)
11. Imperial College London (帝国理工学院)
12. Taichi Graphics
13. Georgia Tech (佐治亚理工学院)
14. The University of Hong Kong (香港大学)
15. University of Pennsylvania (宾夕法尼亚大学)
16. University of Utah (犹他大学)
17. University of Washington (华盛顿大学)
18. University of Michigan (密歇根大学)
19. University of Texas at Austin (德克萨斯大学奥斯汀分校)
20. MIT-IBM Watson AI Lab

### 核心团队成员(47人)
包括Zhou Xian, Yiling Qiao, Zhenjia Xu, Tsun-Hsuan Wang等47位核心贡献者,以及Yuanming Hu, Guanya Shi, Lingjie Liu, Zackory Erickson, David Held, Minchen Li, Linxi "Jim" Fan, Yuke Zhu, Wojciech Matusik, Shuran Song, Daniela Rus, Ming Lin, Bo Zhu, Katerina Fragkiadaki, Chuang Gan等知名学者作为指导。

## 技术架构

### 统一物理引擎
Genesis的核心是一个从底层重新设计和构建的通用物理引擎,它将各种物理求解器及其耦合集成到统一框架中。

### 生成代理框架
在核心物理引擎之上,Genesis进一步增强了一个在上层运行的生成代理框架,旨在实现机器人及更广泛领域的全自动数据生成。

## 应用场景

1. **机器人学习**: 生成机器人训练数据,包括操作和运动策略
2. **具身AI**: 为具身AI代理提供交互式3D环境
3. **物理AI**: 生成物理准确的仿真数据
4. **自动驾驶**: 生成驾驶场景和传感器数据
5. **虚拟工厂**: 在虚拟工厂中训练虚拟机器人

## 技术优势

1. **通用性**: 支持广泛的材料和物理现象
2. **高性能**: 超快速的仿真和渲染
3. **易用性**: Python友好,用户友好
4. **生成能力**: 从自然语言生成多模态数据
5. **真实感**: 照片级真实感渲染
6. **可部署性**: 生成的策略可部署到真实世界

## 与其他仿真引擎的对比

根据2024年12月的报道,Genesis在物理模拟速度方面比现有的GPU加速仿真引擎更快,这得益于:
- GPU加速的并行计算技术
- 优化的碰撞检测
- 自动休眠机制
- 接触岛(contact island)等特性

## 市场定位

Genesis定位为"生成模型的真实物理引擎",旨在为生成式AI提供物理准确的仿真基础,特别是在机器人和具身AI领域。

---

**调研时间**: 2026年2月26日  
**来源**: 官网、GitHub、技术报道


## GitHub仓库详细信息

**GitHub地址**: https://github.com/Genesis-Embodied-AI/Genesis  
**Stars**: 28.2k ⭐  
**Forks**: 2.6k  
**许可证**: Apache-2.0  
**最新版本**: v0.3.0 (2025年8月5日发布)

### 关键特性

#### 1. 速度性能
- **超高速**: 在单个RTX 4090上模拟Franka机械臂时超过4300万FPS
- **实时倍数**: 比实时快43万倍

#### 2. 跨平台支持
- **操作系统**: Linux, macOS, Windows
- **计算后端**: CPU, Nvidia GPU, AMD GPU, Apple Metal

#### 3. 多物理求解器集成
- 刚体(Rigid body)
- MPM (Material Point Method, 物质点法)
- SPH (Smoothed Particle Hydrodynamics, 光滑粒子流体动力学)
- FEM (Finite Element Method, 有限元法)
- PBD (Position Based Dynamics, 基于位置的动力学)
- Stable Fluid (稳定流体)

#### 4. 广泛的材料模型
支持以下材料的模拟和耦合:
- 刚体(Rigid bodies)
- 液体(Liquids)
- 气体(Gases)
- 可变形对象(Deformable objects)
- 薄壳对象(Thin-shell objects)
- 颗粒材料(Granular materials)

#### 5. 机器人兼容性
支持多种机器人类型:
- 机械臂(Robotic arms)
- 腿式机器人(Legged robots)
- 无人机(Drones)
- 软体机器人(Soft robots)

支持加载格式:
- MJCF (.xml)
- URDF
- .obj, .glb, .ply, .stl等

#### 6. 照片级真实感渲染
- 原生光线追踪渲染
- 高质量视觉输出

#### 7. 可微分性
Genesis设计为完全可微分:
- **当前支持**: MPM求解器和Tool求解器
- **未来计划**: 刚体和关节体求解器(从下一版本开始)

#### 8. 用户友好性
- 简洁的安装流程
- 直观的API设计
- Python友好

### 快速安装

#### 方法1: 使用pip
```bash
# 先安装PyTorch
# 然后安装Genesis
pip install genesis-world  # 需要Python>=3.10,<3.14

# 或安装最新版本
pip install git+https://github.com/Genesis-Embodied-AI/Genesis.git
```

#### 方法2: 可编辑模式(开发者)
```bash
git clone https://github.com/Genesis-Embodied-AI/Genesis.git
cd Genesis
pip install -e ".[dev]"
```

#### 方法3: 使用uv(快速包管理器)
```bash
# 安装uv
curl -LsSf https://astral.sh/uv/install.sh | sh  # macOS/Linux
# 或
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"  # Windows

# 克隆并安装
git clone https://github.com/Genesis-Embodied-AI/Genesis.git
cd Genesis
uv sync

# 安装PyTorch
uv pip install torch --index-url https://download.pytorch.org/whl/cu126  # NVIDIA GPU
# 或
uv pip install torch --index-url https://download.pytorch.org/whl/cpu  # CPU
# 或
uv pip install torch  # Apple Silicon

# 运行示例
uv run examples/rigid/single_franka.py
```

### Docker支持

#### NVIDIA GPU
```bash
# 构建镜像
docker build -t genesis -f docker/Dockerfile docker

# 运行容器
xhost +local:root
docker run --gpus all --rm -it \
-e DISPLAY=$DISPLAY \
-e LOCAL_USER_ID="$(id -u)" \
-v /dev/dri:/dev/dri \
-v /tmp/.X11-unix/:/tmp/.X11-unix \
-v $(pwd):/workspace \
--name genesis genesis:latest
```

#### AMD GPU
```bash
# 构建镜像
docker build -t genesis-amd -f docker/Dockerfile.amdgpu docker

# 运行容器
docker run -it --network=host \
 --device=/dev/kfd \
 --device=/dev/dri \
 --group-add=video \
 --ipc=host \
 --cap-add=SYS_PTRACE \
 --security-opt seccomp=unconfined \
 --shm-size 8G \
 -v $PWD:/workspace \
 -e DISPLAY=$DISPLAY \
 genesis-amd

# 注意: AMD用户需要使用ROCm (HIP)后端
# gs.init(backend=gs.amdgpu)
```

### 文档资源

**多语言文档**:
- 英文: https://genesis-world.readthedocs.io/en/latest/
- 中文: https://genesis-world.readthedocs.io/zh-cn/latest/
- 日文: https://genesis-world.readthedocs.io/ja/latest/

包含:
- 详细的安装步骤
- 教程
- API参考

### 贡献指南

Genesis是一个开放协作的项目,欢迎社区贡献:
- Pull requests (新功能或bug修复)
- Bug报告 (通过GitHub Issues)
- 改进建议

详见贡献指南: CONTRIBUTING.md

### 支持渠道

- **Bug报告/功能请求**: GitHub Issues
- **讨论/提问**: GitHub Discussions
- **社区**: Discord, Wechat群

### 发布历史

- **v0.3.0** (2025年8月5日): 最新版本
- **v0.2.1** (2025年1月8日): 性能优化
- **v0.2.0** (2024年12月): 初始公开版本

### 性能基准测试

2025年1月9日发布了详细的性能基准测试和比较报告,包含所有测试脚本。

### 官方支持

自2025年7月2日起,Genesis的开发获得Genesis AI公司的官方支持。

### 致谢

Genesis的开发得益于以下开源项目:
- **Taichi**: 高性能跨平台计算后端
- 其他多个开源项目

### 相关论文

Genesis项目关联多篇学术论文,涵盖生成框架的各个模块,部分论文仍在投稿中。

### 引用

如果您在研究中使用Genesis,请引用相关论文。

---

**调研更新时间**: 2026年2月26日
