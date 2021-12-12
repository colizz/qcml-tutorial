# cmschina-dnn-tutorial

请在 hands-on 开始前先配好环境。如果您有 CERN lxplus 或 高能所 lxslc 集群的账号，请尽量在这个集群上面部署环境并完成练习。没有上述集群账号的同学请用冬令营提供的 PKU 集群进行练习。

对于使用 lxplus 或 lxslc 的同学，请按如下方法设置：

1. 首先，请创建一个新的目录，并进入。
2. 随后直接复制粘贴执行如下命令，即完成环境配置。
    
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
    
    ## Launch the jupyter service (your can use any port number below)
    hostname
    jupyter lab --port 8989 --no-browser
    ```
    
3. 要保持上面的 terminal 不断，这样 Jupyter 服务就会一直保持。记下上面 hostname 输出的机器的名字，然后在个人笔记本新打开一个 terminal，把本地和远端的端口连接起来：
    
    ```bash
    ssh -L 8989:localhost:8989 <username>@<hostname>
    ```
    
4. 在浏览器打开 [http://localhost:8989](http://localhost:8989)，大功告成！

对于使用 PKU 集群的同学，您也可以直接进入搭建好的 JupyterHub 环境（参见集群使用的 qq 文档，直接用浏览器访问）。随后您可以选择 `wintercamp_ml` 的 conda 环境完成练习。当然您也可以按照上面的步骤自行搭建环境。

搭好环境后，可以 clone 本练习仓库

```bash
git clone https://gitee.com/colizz/cmschina-dnn-tutorial.git
```

随后可以用 Jupyter 打开相关 notebook，参照本课程讲稿进行练习。对使用 PKU 集群官方 JupyterHub 的同学，请记得在 notebook 中选择 kernel 为 `wintercamp_ml`。