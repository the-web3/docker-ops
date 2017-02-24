# 轻松玩转docker
## 第一章：Docker简介

## 第二章：不同的平台上安装Docker与使用
### 第一节:Mac平台上Docker安装与使用
 Docker是一个跨平台的轻量级虚拟机，可移植性非常高，一次部署，终生可用。Docker可以在Linux,Windows,MacOS等平台上安装使用。我们都知道Linux有很多不同        的版本，例如Ubuntu，AIX，CentOS，Debian，Fedora，Oracle Linux，Red Hat Enterprise Linux，openSUSE and SUSE Linux Enterprise等。尽管Linux的版本很多，但是我们的Docker都可以在他们在面运行。你也可以使用Docker云来自动准备和管理你的云实例。
#### 1.在Mac系统上安转Docker
Docker的Mac系统上的安装包中包含了你在Mac上运行Docker的所有依赖的东西，下面这个主题是描述在Mac系统上预安装需要考虑的一些问题和怎样在Mac系统上安装  Docker。
_你的Mac本上是否已经安装了Docker,如果已经安装了Docker，你可以直接去启动Docker，如果你已经掌握了在Mac上使用Docker，那么你可以直接跳过整个Mac上的Docker的安装和运行部分。_
#### 1.2.在Mac下载Docker
在Mac系统上下载Docker有两种方式，一种是下载stable Docker，另一种是下载Beta版本的Docker
#### 1.3.stable Docker下载
稳定版的Docker是完全测试过的，并且在Docker引擎中带有实验特征的最新版本的Docker引擎，这种引擎在默认情况下启用并其在Docker Daemon设置中优先配置为实验模式。如果你想依赖平台来工作那么这种安装方式是最好的选择。这些版本遵循比beta版更长的发布时间版本计划，与Docker Engine版本和修补程序同步。在稳定通道上，您可以选择是否发送使用统计信息和其他数据。
`下载地址：https://download.docker.com/mac/stable/Docker.dmg`
###### Docker实验的特征
下面将例举实验版的Docker的特征，实验特征不是为了成型的产品准备的，他们是用来测试和评估你的`sandbod`环境的，下面信息描述了每一个特征和在github上拉取下来的与之相关的争议。如果是必要的争议信息会提供争议相关的文档。如果你是一个社区上的Docker的活跃使用用户，希望你可以在这些特征上提供一些你希望的建议。
###### 使用实验版的Docker
实验特征现在包含标准的1.13.0版本的Docker二进制文件， 为了使实验特征能使用，你需要`--experimental`来启动Docker守护进程，你可以通过使用`/etc/docker/daemon.json`使守护标志能用。例如：

    {
               "experimental": true
    }
然后确认实验标志是可以使用的
      
    $ docker version -f '{{.Server.Experimental}}'
    true
###### 目前的实验特征
额外的图形驱动插件
Ipvlan网络驱动器
Docker堆栈和分布式应用程序软件集
检查点和恢复
###### 怎么样评判这些特征
此处的内容没什么用，主要是关于这些特征的更改建议。
##### 1.4.Beta Docker下载
这个安装包提供了最新适应Mac系统的Docker的Beta发布版本，在Docker引擎中提供了带有实验特征的切掉边缘效应，这种引擎在默认情况下启用并其在Docker Daemon设置中优先配置为实验模式。如果你想在开发模式下实验特征这是最好的使用通道，并且能经受得住一些非稳定性和bugs。这个通道是Beta程序的延续，为了应用程序的进化你可以提供一些相关的反馈。Beta通道的版本发布比Stable通道更频繁，经常一个发布一次或者多次。我们通过板来收集所有的用户数据。
 `下载地址：https://download.docker.com/mac/beta/Docker.dmg`
###### 重要提示
Mac需要在运行OS X El Capitan 10.11的2010年或更新的Mac上，或更高版本的macOS版本，英特尔支持MMU虚拟化。该应用程序将在10.10.3 Yosemite上运行，但支持有限。请看安装前需要知道什么的完整的预备知识解释。你可在beta和stable版本之间转换，但是在同一时刻你必须只能安装一个应用程序。在安装另一个之前卸载这个只是如果你想保存以前的那个Docker你需要保存镜像和导出容器。想要知道更多，请看https://docs.docker.com/docker-for-mac/faqs/#stable-and-beta-channels。
###### 在Mac系统上安装Docker你需要知道些什么
首先你需要了解Docker ToolBox和Docker Machine：如果你已经在你的机器上运行Docker，首要条件就是阅读Docker for Mac和Docker ToolBox来理解已经存在的设置对这个安装的影响。怎样在Mac系统下配置你的环境和怎样使两个产品能够共同协作。

Docker机器的相关联系：在Mac上安装Docker不会影响你创建的机器。你可以选择从本地默认机器获取选择复制镜像和容器到新的Mac上的Docker HyperKit”虚拟机。当你在Mac上运行Docker，不用需要Docker虚拟机运行在本地（它可以运行在任何地方）。Mac系统上的Docker，你有一个新的、本地的虚拟系统来取代虚拟盒子系统运行（这个东西叫做HyperKit）。想要学更多的话，请看下面的Docker for Mac和Docker ToolBox。

_系统需求：只有满足所有这些要求时，Mac版Docker才会启动_
* Mac必须是因特尔硬件支持内存管理单元（MMU）虚拟化的2010版或者更新的版本。例如：扩展页表（EPT）和非限制模式。
* 支持OS X El Capitan 10.11和更高版本的MacOS。 至少，Docker for Mac需要macOS Yosemite 10.10.3或更新版本，注意使用10.10.x是有一定的风险的。
* 从Docker for Mac稳定版1.13（即将推出）和并发Beta版本开始，我们将不再解决OS X Yosemite 10.10特有的问题。 在将来的版本中，由于OS X版本的弃用状态，Docker for Mac可能会停止在OS X Yosemite 10.10上运行。建议升级到最新版本的macOS。
* 至少4GB的内存
* 不能安装版本4.3.30之前的VirtualBox（它与Mac的Docker不兼容）

_注意.如果你的系统是不满足这些要求的，你能安装Docker Toolbox,使用甲骨文的虚拟盒子来代替HyperKit_
安装包括:Docker Engin, Docker CLi,Docker Compose和Docker Machine

##### 1.5.Mac上安装和运行Docker
* 双击`Docker.dmg`打开安装包，然后拖拽Moby蓝鲸到应用文件夹。在安装过程中你将会被Docker.app请求输入你电脑的系统密码。给予进入特权的需要安装网络组件和链接到Docker应用程序。
![a][a]
[a]:https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/1.jpg "a"

* 双击Docker.app启动Docker
![d][d]
[d]:https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/2.jpg "d"

* 蓝鲸的头状态条表Docker正在运行，并且是可以从终端进入的。如果你已经安装了这个app，你也会获得暗示下一步成功的消息和链接到这个文档，点击蓝鲸图标在状态条上有下图这样一个显示和弹出
![b][b]
[b]:https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/3.jpg "b"

* 点击鲸获取参数和其他选项
![c][c]
[c]:https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/14.jpg "c"

* 选择关于Docker以验证您是否具有最新版本

#### 恭喜你，你已经完成Mac下面的Docker安装。

#### 2.Mac平台下Docker相关的东西
#### 2.1.开始使用Docker for Mac
Docker是一个创建集装箱式的全开发平台应用程序，在Mac平台上运行Docker最好的方法就是在Mac平台上启动Docker
 
_注意:如果你还没有在Mac平台上安装Docker，请你现在Mac平台上安全稳定版的Docker或者Beta版本的Docker，在安装之前你必须了解Docker
对Mac系统的安装需求，你可以先看上面提道的安装前你需要知道的东西。_

#### 2.2.检查Docker Engine，Docker Compose和Docker Machine的版本
如果你的docker，docker-compose和docker-machine是能与Docker.app兼容的最新版本，那么你就可以运行下面这些命令
    
    $ docker --version
    Docker version 1.13.0, build 49bf474

    $ docker-compose --version
    docker-compose version 1.10.0, build 4bd6f1a

    $ docker-machine --version
    docker-machine version 0.9.0, build 15fd4c7
_注意.这上面只是一个例子，你的输出结果根据你的版本不同而不同_ 

#### 2.2. 浏览应用程序和运行一个案列
* 打开命令行终端，使用Docker命令检查Docker是不像所期望的那样正常工作。可以使用这些命令docker version, docker ps和docker run hello-world来确认Docker是否正常运行，如果这些命令能正常执行,那么就说Docker在运行着。
* 使用更刺激的方法，运行一个Docker化的web服务器，当然这样做的前提条件是你本地必须有你要运行的镜像。
  
`docker run -d -p 80:80 --name webserver nginx`
      
![c][c]
[c]:https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/5.jpg "c"

_如果本地没有找到这个镜像，那么Docker将会去Docker Hub中拉取镜像。_
