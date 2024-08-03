# 量子计算与机器学习研讨会 —— Transformer 学习教程

本仓库是为 2024 年于长春举办的量子计算与机器学习研讨会准备的 Transformer 相关的教程资料。讲义内容以`Jupyter Notebook`写成。

## 代码使用

### 方法1：在 Google Colab 上直接打开运行（方便，推荐）

可以直接在 Google Colab 上打开 Jupyter 并运行使用

| Section | Google Colab |
| --- | --- |
| [`chap1_basis.ipynb`](chap1_basis.ipynb) | 看视频不用打开 Colab |
| [`chap2_transformer_anatomy.ipynb`](chap2_transformer_anatomy.ipynb) | [用 Colab 打开](https://colab.research.google.com/github/colizz/qcml-2024-tutorial/blob/master/chap2_transformer_anatomy.ipynb) |
| [`chap3_transformer_training.ipynb`](chap3_transformer_training.ipynb) | [用 Colab 打开](https://colab.research.google.com/github/colizz/qcml-2024-tutorial/blob/master/chap3_transformer_training.ipynb) |

### 方法2：在高能所 lxslc 集群上通过预装的 `Jupyter Lab` 运行

在本地打开两个终端。

第一个终端中，登录高能所 lxslc 集群，然后执行
 ```bash
cd <进到喜欢的目录>
git clone https://gitee.com/colizz/qcml-2024-tutorial .
cd qcml-2024-tutorial

hostname # 看一下当前进入的是哪个节点，例如lxslc702
source /scratchfs/cms/licq/miniconda/bin/activate # 这里进入一个已经配好的conda环境
conda activate ml

jupyter lab --no-browser # 启动jupyter lab，看看jupyter lab被运行在哪个端口上，例如8888
 ```

然后第一个终端就挂住不动了。在第二个终端，把本地的端口绑定到第一个终端中读到的 *lxslc节点* （如lxslc702）和 *Jupyter端口* (如8888）上
 ```bash
ssh -L 8888:localhost:8888 <你的用户名>@lxslc702.ihep.ac.cn # 修改8888和lxslc702
 ```
 
最后在浏览器中输入上面 Jupyter 返回的 http://localhost:8888 开头的一串网址，大功告成！
