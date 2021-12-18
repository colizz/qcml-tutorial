# cmschina-dnn-tutorial

## 开启 Jupyter 服务

您可以使用 PKU 集群、THU 集群、或高能所集群，按照下面的方式开启 Jupyter 服务从而运行本仓库中的 Jupyter notebook。

首先进入集群，并克隆本仓库：

```bash
git clone https://gitee.com/colizz/cmschina-dnn-tutorial.git
```

1. 使用 PKU 集群

您可以直接进入搭建好的 JupyterHub 环境（参见集群使用的 qq 文档，直接用浏览器访问）。随后打开相应的 notebook 文件后，在 kernel 处选择 `wintercamp_ml` 的 conda 环境，即可执行代码完成练习。

2. 使用 THU 集群或高能所集群

进入集群后，请首先 source 相应的环境（需要的 conda 环境已经部署在作者的个人目录下）：

```bash
# 若在 THU 集群，执行：
source /home/storage4/users/congqiaoli/miniconda/bin/activate
conda activate ml

# 若在高能所集群，执行：
source /scratchfs/cms/licq/miniconda/bin/activate
conda activate ml
```

随后开启个人的 Jupyter 服务，并部署在机器的某端口。选择 5000~9999 之间的任意端口，下面以 8989 为例（不同用户在一台机器上开启的服务，不能部署到同一个端口上）。

```
jupyter lab --no-browser --port 8989
```

这将开启一个 Jupyter 服务，此服务需在后面练习的过程中一直保持开启。

随后，在个人笔记本打开一个本地的终端（Windows 用户可用命令提示符），将本地的 8989 端口与远端的 8989 端口连接起来。输入的命令为在一般使用的 ssh 连接命令的基础上额外加上 `-L 8989:localhost:8989` 。这个 ssh 的连接也需要一直保持不断。

最后在浏览器中输入上面 Jupyter 返回的 http://localhost:8989 开头的一串网址，大功告成！

## 附录

作为参考，本练习所用的 conda 环境建立方式如下：

```bash
## Download Miniconda
wget --no-check-certificate https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh -b -p ./miniconda
source miniconda/bin/activate

## Create new conda environment "ml"
conda create --name ml python==3.9 -y
conda activate ml

pip install jupyterlab
pip install numpy pandas scikit-learn scipy matplotlib PyYAML # classical analysis packages for python
pip install uproot coffea uproot3 awkward0 lz4 xxhash tables # processing ROOT file for HEP
pip install tensorflow tensorboard sklearn # ML packages: tensorflow/keras
pip install torch # ML package: pytorch
```
