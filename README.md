# CMS China 2nd 冬令营机器学习教程

本仓库是为CMS China 2nd冬令营的机器学习教程资料。讲义内容以`Jupyter Notebook`写成。

## 代码使用（在高能所lxslc集群的上使用 `Jupyter Lab`）

在本地打开两个终端。

第一个终端中，登录高能所 lxslc 集群，然后执行
 ```bash
cd <进到喜欢的目录>
git clone https://gitee.com/colizz/cmschina-2nd-ml-tutorial .
cd cmschina-2nd-ml-tutorial

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
