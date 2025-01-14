# 第一届机器学习和量子计算冬季学校 —— Transformer 学习教程

本仓库是为 2025 年 1 月于南开大学承办的机器学习和量子计算冬季学校准备的 Transformer 相关的教程资料。讲义内容以`Jupyter Notebook`写成。

## 代码使用

### 方法1：在 Google Colab 上直接打开运行

可以直接在 Google Colab 上打开 Jupyter 并运行使用

| Section | Google Colab |
| --- | --- |
| [`chap1_pytorch_basics.ipynb`](chap1_pytorch_basics.ipynb) | [用 Colab 打开](https://colab.research.google.com/github/colizz/ml-tutorial/blob/v2025-01-nku/chap1_pytorch_basics.ipynb) |
| [`chap2_transformer_anatomy.ipynb`](chap2_transformer_anatomy.ipynb) | [用 Colab 打开](https://colab.research.google.com/github/colizz/ml-tutorial/blob/v2025-01-nku/chap2_transformer_anatomy.ipynb) |
| [`chap3_transformer_training.ipynb`](chap3_transformer_training.ipynb) | [用 Colab 打开](https://colab.research.google.com/github/colizz/ml-tutorial/blob/v2025-01-nku/chap3_transformer_training.ipynb) |
| [`chap4_transformer_advanced_usage.ipynb`](chap4_transformer_advanced_usage.ipynb) | [用 Colab 打开](https://colab.research.google.com/github/colizz/ml-tutorial/blob/v2025-01-nku/chap4_transformer_advanced_usage.ipynb) |

### 方法2：在高能所集群上通过预装的 `Jupyter Lab` 运行

在本地打开两个终端。

第一个终端中，登录高能所集群
```bash
ssh <用户名>@lxlogin.ihep.ac.cn
```

然后执行
 ```bash
cd <进到喜欢的目录>
git clone https://github.com/colizz/ml-tutorial.git -b v2025-01-nku
## 或者尝试 git clone https://gitee.com/colizz/ml-tutorial.git -b v2025-01-nku

cd ml-tutorial

hostname # 看一下当前进入的是哪个节点，例如lxlogin004
source /scratchfs/cms/licq/miniconda3-el9/bin/activate # 这里进入一个已经配好的conda环境
conda activate weaver-uproot5

jupyter lab --no-browser # 启动jupyter lab，看看jupyter lab被运行在哪个端口上，例如8888
 ```

然后第一个终端就挂住不动了。在第二个终端，把本地的端口绑定到第一个终端中读到的 *lxlogin节点* （如lxlogin004）和 *Jupyter端口* (如8888）上
 ```bash
ssh -L 8888:localhost:8888 <用户名>@lxlogin004.ihep.ac.cn # 修改8888和lxlogin004
 ```
 
最后在浏览器中输入上面 Jupyter 返回的 http://localhost:8888 开头的一串网址，即可打开 Jupyter Lab 页面。

## 内容摘要

第一节作为预备章节，将简要介绍 PyTorch 的知识，了解基本原理并熟悉一些常用函数和模块的使用（预计30分钟）。

第二节将在自然语言处理领域的背景下介绍 Transformer 的基础知识，用 PyTorch 从零搭建一个 Transformer 模型，实现对各个组分的代码进行深入理解（预计60分钟）。

第三节将在高能物理实验中事例分类问题进行实战：我们利用 PyTorch + pytorch-lightning 搭建工作流，分别训练一个基础的 MLP 网络，和上节中从零搭建起来的 Transformer 模型；我们会讨论 Transformer 用作分类器的一些要点。最后，我们利用 PyTorch 内建的模块对 Transformer 代码进行简化（预计60分钟）。

第四节将讨论一些前沿的 Transformer 在粒子物理领域开发和应用的进展。我们关注如何针对粒子格式的数据设计性能更优秀的 Tranformer：通过粒子对的不变质量信息作为额外输入，为模型提供 inductive bias。我们从上节的 Transformer 模型开始修改，最终形成类似 Particle Transformer (ParT) 的架构，并讨论由此获得的性能提升。利用已经搭建好的数据流，我们最后提供一个接入 ParT 和 ParticleNet 标准模型文件的接口，利用这些前沿模型训练我们的任务。这为未来在不同的科研场景中适配这些模型提供了一个参考案例（预计60分钟）。
