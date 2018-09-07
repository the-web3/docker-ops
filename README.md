# 轻松玩转docker
## 第一章：Docker简介
### 第一节.概述
Docker是唯一一能够应对整个混合云中的每个应用的提供集装箱服务的平台。 现在很多企业面临着数字化转型的压力，受到现有应用程序和基础架构的制约，很难有很好的发展。而Docker合理利用日益多样化的云，数据中心和应用程序架构产品组合。 真正实现了应用程序和基础架构与开发人员和IT操作员之间的真正独立性，以释放他们的潜力并创建更好的协作和创新模式。

Docker是开发，运维和运行应用程序的开放平台。 Docker使您能够将应用程序与基础架构分开，以便您可以快速交付软件。 使用Docker，您可以像管理应用程序一样管理基础架构。 通过利用Docker的优点，快速进行运维，测试和部署代码，可以明显地缩短编写代码，以及在生产环境中运行代码之间的延迟的时间。真正实现与平台解耦合。

#### 1.Docker平台

Docker提供了在称为容器的松散隔离环境中打包和运行应用程序的能力。 隔离和安全性允许您在给定主机上同时运行多个容器。 容器是轻量级的，因为它们不需要管理程序的额外负载，而是直接在主机的内核中运行。 这意味着，与使用虚拟机相比，您可以在给定的硬件组合上运行更多的容器。 你甚至可以在实际上是虚拟机的主机中运行Docker容器！

Docker提供工具和平台来管理容器的生命周期：

* 使用容器开发您的应用程序及其支持组件。
* 容器成为分发和测试你的应用程序的单元。
* 准备好后，将您的应用程序部署到生产环境中，作为容器或协调服务。 无论您的生产环境是本地数据中心，云提供商还是两者的混合，这都是一样的。

#### 2.我们可以使用Docker来做什么

1).快速，一致地交付您的应用程序

通过允许开发人员使用提供应用程序和服务的本地容器在标准化环境中工作，Docker简化了开发生命周期。 容器非常适合持续集成和持续交付(CI/CD)工作流程。

考虑以下示例场景：

* 开发人员在本地编写代码并使用Docker容器与他们的同事分享他们的工作。
* 使用Docker将他们的应用程序推入测试环境并执行自动和手动测试。
* 当开发人员发现错误时，他们可以在开发环境中修复它们，并将它们重新部署到测试环境进行测试和验证。
* 测试完成后，向客户提供修补程序与将更新后的图像推送到生产环境一样简单。

2).响应式部署和缩放

Docker的基于容器的平台支持高度可移植的工作负载。 Docker容器可以在开发人员的本地笔记本电脑上，数据中心的物理或虚拟机上，云提供程序上或混合环境中运行。

Docker的可移植性和轻量级特性也使得动态管理工作负载变得非常容易，可以近乎实时地按业务需求扩展或拆分应用程序和服务。

3).在同一个硬件上运行更多的工作负载

Docker轻量且快速。 它为基于虚拟机管理程序的虚拟机提供了一种可行，经济高效的替代方案，因此您可以使用更多计算容量来实现业务目标。 Docker非常适合高密度环境和中小型部署，您需要以更少的资源实现更多功能。

### 第二节.docker标准化开发，发行和部署
docker将软件打包成标准化的单元用于开发，发行和部署，容器镜像是轻量级可独立执行软件包，包含运行它所需的所有内容：代码，runtime，系统工具，系统库，设置。 不管环境如何，集装箱化软件都可以运行相同的Linux和Windows环境上。 容器将软件与其周围环境隔离开来，例如开发环境和生产环境之间的差异，并有助于减少在同一基础架构上运行不同软件的团队之间的冲突。下图是一个简单的结构图

图片0： 
    ![图片0](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/19.png  "图片0")


## 第二章：不同的平台上安装Docker与使用
### 第一节:Mac平台上Docker安装与使用
 Docker是一个跨平台的轻量级虚拟机，可移植性非常高，一次部署，终生可用。Docker可以在Linux,Windows,MacOS等平台上安装使用。我们都知道Linux有很多不同的版本，例如Ubuntu，AIX，CentOS，Debian，Fedora，Oracle Linux，Red Hat Enterprise Linux，openSUSE and SUSE Linux Enterprise等。尽管Linux的版本很多，但是我们的Docker都可以在他们在面运行。你也可以使用Docker云来自动准备和管理你的云实例。
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
图片1： 
    ![图片1](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/1.jpg  "图片1")

* 双击Docker.app启动Docker
图片2： 
    ![图片2](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/2.jpg  "图片2")

* 蓝鲸的头状态条表Docker正在运行，并且是可以从终端进入的。如果你已经安装了这个app，你也会获得暗示下一步成功的消息和链接到这个文档，点击蓝鲸图标在状态条上有下图这样一个显示和弹出
图片3： 
    ![图片3](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/3.jpg  "图片3")

* 点击鲸获取参数和其他选项
图片14： 
    ![图片14](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/14.jpg  "图片14")

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
图片5： 
    ![图片5](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/5.jpg  "图片5")

_如果本地没有找到这个镜像，那么Docker将会去Docker Hub中拉取镜像。_
_注意:早期的Beta发布版本使用docker做为主机名来创建URL，现在端口号被暴露在虚拟机的私有IP地址并且在没有主机名字设置的情况下传递给主机，也可以看Beta9的发布注意点。_

* 在你的web服务器正在运行的时候执行`docker ps`查看web服务器容器的详细信息。
* 停止或者移除容器和镜像
nginx web服务器在你停止或者移除容器之前会持续运行着，如果你想停止web服务器:`docker stop webserver`,启动服务器用命令`docker start webserver`。查看一个容器是否停止了用命令`docker ps`; `docker ps -a`查看终止状态的容器。使用`docker rm -f webserver`命令来移除正在运行的容器。这个命令会移除容器，但不能移除`nginx`镜像。你可以使用docker list命令来列出本地镜像。你可能会保存一些镜像在本地以致于你不用再次去Docker Hub中拉镜像。想要移除一个长期不需要的镜像，使用docker rmi后加ID号和镜像名字。例如，docker rmi ngix。

* 命令总结:

`docker ps` 查看正在运行的容器

`docker stop`停止正在运行的容器

`docker start`启动容器

`docker ps -a`查看终止状态的容器

`docker rm -f webserver`命令来移除正在运行的容器

`docker list` 列出本地镜像

`docker rmi` 删除的镜像

#### 2.3.Preferences
选择，蓝鲸图标-->菜单条中的Preferences。你可以设置下面的运行时间选项
##### General
图片6： 
    ![图片6](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/6.jpg  "图片6")

##### 自动启动，更新，备份，使用数据
* Mac平台下的Docker设置当你登录的自动启动Docker。如果你想在开启你的对话时不启动Docker就不需要检查这个选项
* Mac平台下的Docker在更新可获得时，设置自动检查更新和告知用户，如果发现一个新版本，点击OK接受安装它(或者取消更新保存当前版本)。如果你不能够检查更新，你仍然可以手动地更新，蓝鲸-->Check for Update 
* 选中从Time Machine备份中排除虚拟机以防止Time Machine备份Mac平台下的虚拟机
* Send usage statistics你可以在Mac平台下设置Docker自动发送诊断、死机报告和用户数据。这些信息能帮助Docker提高应用程序和获取更多关于故障问题排除的内容。不检查这个opt输出和防止自动发送数据。在这些情况下Docker可能提供更多信息，甚至自动发送可用。

##### File sharing 
图片7： 
    ![图片7](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/7.png  "图片7")
    
你能够用它来决定在你的Mac平台上的目录是否是容器共享
* Add a Directory-点击`+`和操纵你想要添加的目录
* 点击Apply & Restart使目录使用Docker的捆绑峰[-v]特征对当前容器有效。所有这些局限性在目录上是能够共享的它们不能成为已经共享的目录的子目录

##### Advanced
###### CPUs
默认情况下，Mac平台上的Docker设置使用2个处理器，你可以通过设置更高的数字来增加处理力度，或者在Mac上降低它以使得使用更少的计算机资源
###### Memory
默认情况下，在Mac平台下的Docker使用2GB的运行内存，这2GB的内存从你的计算机的总可用内存中分配。你可以通过设置更高的内存来提高应用程序的性能例如设置为3，如果你想要使用更少的内存那么你就把它设置到1。
###### Storage location
你可设置Linux容量存在位置，例如：容器和镜像被存储在那里。Disk images localtion(Beta)启动Beta39，存储的镜像关联到硬盘镜像，并且被应用程序跟踪。如果你尝试移动镜像到已经存在一个镜像的本地，你将获得一个温馨提示，你是否想替换已经存在的镜像。对于Beta提前发布的版本，在这个对话中的标志已经更新如下

* Storage location被重命名为Disk image location
* Change location按钮被重命名为move disk image
图片8： 
    ![图片8](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/8.png  "图片8")

##### HTTP 代理设置
在Mac平台上的Docker将探测HTTP/HTTPS代理设置和自动地将这些设置传播到Docker和传播到你的容器。例如，如果你把的代理设置设置成`http://proxy.example.com`,当拉容器的时候，Docker将使用这个代理设置。

图片9： 
    ![图片9](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/9.png  "图片9")

#####  Docker Daemon
你可以通过在Docker守护进程配置项中设置怎么样运行容器。你可以在守护进程中配置一些交互式设置或者转换到Advanced直接编辑JSON。基本对话框提供的设置也可以直接在JSON中配置，此版本只是介绍一些常见的设置，使其更容易配置它们。
图片10： 
    ![图片10](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/10.png  "图片10")

* 实验模式
* 自定义注册
* 编辑守护配置文件

下面将会详细介绍着三种模式

#####  Experimental mode

在Mac平台上启动的Stable1.13.0和Beta31版本的Docker，这两种发布版本在Docker引擎上都有各自的实验特征。这部分内容在github上的Docker实验特征的的ReadMe中有介绍。实验特征是不适合于生产环境或者工作负载的。它们意味着对新想法的沙盒实验，许多实验特征可能会合并到即将发布的stable版本中，但是其他的从随后的Beta版本中可能的修饰和提高绝不会发布在Stable版本中。在Beta和Stable发布的版本中，你可打开或者关闭实验模式。不管你打开还是关闭它，Mac平台上的Docker会使用目前Docker引擎中常用的使用模式。不管你是不是以实验模式运行，你都可以通过`docker version`这个命令来检查Docker的版本。实验模式的数据将在`Server`下列出。如果`Experimental`是`true`，那么Docker将以实验模式运行，结果显示在下面。（如果false，Experiment模式是关闭）。

    $ docker version
    Client:
     Version:      1.13.0-rc3
     API version:  1.25
     Go version:   go1.7.3
     Git commit:   4d92237
     Built:        Tue Dec  6 01:15:44 2016
     OS/Arch:      darwin/amd64

    Server:
     Version:      1.13.0-rc3
     API version:  1.25 (minimum version 1.12)
     Go version:   go1.7.3
     Git commit:   4d92237
     Built:        Tue Dec  6 01:15:44 2016
     OS/Arch:      linux/amd64
     Experimental: true

##### Custom registries
一种可选的方案使用Docker Hub或Docker Trusted Registry来存储你的公有或者私有镜像，你能使用Docker来设置你的非安全注册，对你本机上的镜像添加URLs来实现非安全注册或者注册镜像。（也可以看FAQs，我怎么添加自定义的CA证书[此处本文后面会写]）

##### 编辑daemon配置文件
在Daemon-->Advanced dialog，你可以通过json文件直接配置Daemon，完全地决定你的容器怎么运行。想看Docker Daemon的完整条目，请看Daemon相关的Docker引擎命令行关联。在编辑完Daemon配置后，点击Apply & Restart来保存它并且重新启动Docker。或者，取消改变，点击tab键，当弹出对话框来询问时选择丢弃或者不应用。
图片11： 
    ![图片11](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/11.png  "图片11")

##### 卸载或者重置
选择 小蓝鲸 ->从菜单条目上选择Preferences，然后在相关对话框上点击Uninstall / Reset。

Uninstall--选择卸载选项是从你的Mac系统中移出DockerReset to factory defaults--选择这个选项重置Mac平台上的Docker使其回到初始状态，就像刚安装的时候一样。你可以通过`<DockerforMacPath> --uninstall`这个命令行来从Mac平台上卸载你的Docker。如果Docker默认安装在本地，下面的命令将提供清除卸载

    $ /Applications/Docker.app/Contents/MacOS/Docker --uninstall
    Docker is running, exiting...
    Docker uninstalled successfully. You can move the Docker application to the trash.

你可能想通过使用命令行来卸载Docker，例如，你发现一个没有功能的APP，你从菜单条目里面无法删除它，那么你就的使用命令行。


##### 安装bash completion
如果你使用bash completion，例如：自制软件在Mac上的bash-completion的bash completion脚本命令能在Docker.app的`Contents/Resources/etc/ `目录里面找到

    docker
    docker-machine
    docker-compose

为了激活bash completion,这些文件需要复制或者软连接到你的bash_completion.d/目录下。例如，如果你使用自制软件

    ln -s /Applications/Docker.app/Contents/Resources/etc/docker.bash-completion /usr/local/etc/bash_completion.d/docker
    ln -s /Applications/Docker.app/Contents/Resources/etc/docker-machine.bash-completion /usr/local/etc/bash_completion.d/docker-machine
    ln -s /Applications/Docker.app/Contents/Resources/etc/docker-compose.bash-completion /usr/local/etc/bash_completion.d/docker-compos

##### Docker Store
从Mac平台下Docker菜单中选择Docker Store，进入Docker应用下载网站。Docker Store是下一代Docker Hub的一个组件，是找到兼容，可信的商业和免费软件和作为Docker镜像发的最佳位置，

### 第二节:Windows平台上Docker安装与使用

#### 1.在windows平台上安装docker
Windows平台上的docker的安装包含docker在Windows平台上运行的所有的依赖包，这里最主要介绍安装前需要考虑的因素和在Windows平台上怎么样下载和安装docker。如果你已经安装了docker，并且准备启动它了。那么你可以跳过此步去学习怎么使用命令行操作docker，docker的配置和docker工具的使用。查看版本发布的注意事项请看`https://docs.docker.com/docker-for-windows/release-notes/`。

#### 2.下载windows平台下的docker
如果你已经做了下载了windows版本下的docker，那么你可以直接安装。windows平台的docker的下载和mac平台下类似，也有两种下载方式。

##### 2.1.stable通道下载
下载地址为：`https://docs.docker.com/docker-for-windows/install/#download-docker-for-windows`
图片15： 
    ![图片15](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/15.png  "图片15")


##### 2.2.edge通道下载
下载地址为：`https://docs.docker.com/docker-for-windows/install/#download-docker-for-windows`
图片151： 
    ![图片151](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/15.png  "图片151")

##### 注意：
windows下的docker要求windows的系统是win10的企业版、教育版和微软虚拟化技术版本的。请您仔细看看你在安装需要了解的所有先决条件清单。虽然你可以选择安装stable通道或者edge通道中的docker，但是在同一个时间段你不能同时安装两个通道中的docker，在你安装另一个版本的docker和卸载这个版本的docker前，你需要保存保存镜像和导出容器。

##### 3、在windows下安装docker前你需要知道的前提条件
 3.1、在windows下运行docker要求的前提条件是微软的虚拟化技术，在微软的虚拟化技术使用的情况下，如果虚拟盒子不能正常工作，但是会有一些虚拟盒子的vm镜像会被保留，通过虚拟盒子创建的`docker-machine`将不再启动。windows下的docker的这些VMs不能并行。即使这样，你也可以使用`docker-machine`来管理这些路由VMs。
 
3.2、目前，docker只能运行企业版和教育版的win10上面，将来会支持更多版本的win10。

3.3、windows平台下的docker创建的容器和镜像和windows主机之间共享所有用户账户。这是因为windows下的用户会使用同一个VM来创建和运行容器。未来windows将会支持隔离用户内容。

3.4、虚拟化得包必须能够支持docker在windows下运行，在windows下安装docker能够使它变得可用，如果你的系统不能够满足这些要求，你需要安装docker box,这样你就可以使用甲骨文的虚拟盒子来代替微软的虚拟化技术，也就说，即使你的操作系统的windows其他版本的，你也可通过使用甲骨文的虚拟盒子装docker，并且使docker变得可用。

3.5、虚拟化技术必须被激活，一般情况下，虚拟化默认是被激活的。更详细的内容请看虚拟化激活排错。

3.6、嵌入虚拟脚本，在VMware中运行一个windows平台下的docker或者一个平行实例，也许能正常工作，但是没有保证。

3.7、windows下安装docker包含哪些东西：安装提供的docker Engine、docker客户的、docker compose项目和Docker Machine.

##### 4、在windows下安装Docker

4.1.双击`InstallDocker.msi`运行安装

4.2.接下来安装向导程序接受指令，接受安装、接下来继续安装

4.3.设置`launch docker`然后完成安装

图片16:
    ![图片16](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/16.png  "图片16")

##### 5.在windows下启动docker
当你安装完成后，docker会自动启动，蓝鲸状态条表面docker正在运行，而且你可以经过终端进入docker。如果你已经安装了运用程序，将会弹出一个成功的进度条然后建议你进行下一步，并且会连接到下面这个文档。当我们初始化完成之后，选择“about docker”点击进去可以看到docker的版本。到此为止，恭喜您，你已经完成在windows启动和运行docker。
图片17:
    ![图片17](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/17.png  "图片17")
    
    
### 第三节、在Linux平台安装docker

#### 1、在Ubuntu下安装docker

##### 1.1.先决条件
在ubuntu下使用docker，你必须确定你满足先决条件，然后安装docker

###### 1.1.1.dockerEE客户端
为了安装docker的企业版本(docker EE),你需要知道Docker EE仓库和你的测试和设备联系。获取这些信息的步骤。
1、输入这个URL地址进入这个网站: `https://store.docker.com/?overlay=subscriptions`。
2、在`Docker Enterprise Edition for Ubuntu`部分中的里面选择 `Get Details/Setup Instructions`这两项。
3、从域区域中拷贝，点击这个即可：`Copy and paste this URL to download your Edition`。
要学习更多关于Docker EE的东西，看这个`Docker Enterprise Edition`部分的内容。

###### 1.1.2.操作系统需求
要想安装docker，你得拥有下面的Ubuntu版本操作系统中的一个
 Yakkety 16.10
 Xenial 16.04 (LTS)
 Trusty 14.04 (LTS)

###### 1.1.2.卸载老版本的docker
比较老一点的版本的docker被叫做docker或者docker-engine，如果你想卸载他们使用下面的命令即可

    sudo apt-get remove docker docker-engine
    
如果`apt-get`报告这些包中没有一个包被安装那么久OK啦。

`/var/lib/docker/`这里面的内容，包括镜像、容器、数据卷、网络是被保藏起来的，DockerCE的包现在被称作docker-ce,dockerEE的包现在被称为docker-ee。

###### 对于Trusty 14.04的操作系统需要安装额外的包
执行下面的命令安装额外的包
   
    $ sudo apt-get update
    
    $ sudo apt-get install \
        linux-image-extra-$(uname -r) \
        linux-image-extra-virtual
        
#### 2.安装docker
你可以根据你的开发需求以不同的方式安装docker。
1、大多数用户通过配置docker容器，并通过docker容器来安装他们的docker，这样可以减少安装和更新的工作量。也就是说自动的，这是这也官方比较推荐的方法。
2、很多用户通过下载DEB包来手动安装并且通过手动更新docker，这也是个有效的解决方案，例如在有缺陷的系统上安装docker是不需要使用网络。

##### 2.1.安装使用仓库
在你第一次在一台新主机上安装docker时，你需要配置一些docker的仓库，然后，你能够从仓库中安装个更新docker。

###### 2.1.设置仓库
设置DockerEE和DockerCE的方式是不同，下面将会介绍这两种仓库的设置
###### DockerCE
1.安装一些允许apt在HTTPS上使用一个仓库

     sudo apt-get install \
        apt-transport-https \
        ca-certificates \
        curl \
        software-properties-common
        
2.添加一个docker官方的GPG密钥
     
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

认证的密钥指纹是`9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88`
3.执行下面的命令

    $ sudo apt-key fingerprint 0EBFCD88

    pub   4096R/0EBFCD88 2017-02-22
          Key fingerprint = 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
    uid                  Docker Release (CE deb) <docker@docker.com>
    sub   4096R/F273FCD8 2017-02-22

4.使用下面的命令来配置stable版本的仓库，你也可以安装edge版本的仓库

stable版本的配置命令

    $ sudo add-apt-repository \
       "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
       $(lsb_release -cs) \
       stable"
       
edge版本的配置命令，在上面命令行stable的后面添加一个edge即可
 
    $ sudo add-apt-repository \
          "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
          $(lsb_release -cs) \
          stable edge" 
       
###### DockerEE 
1.安装一些包允许apt通过HTTPS使用仓库

    $ sudo apt-get install \
        apt-transport-https \
        ca-certificates \
        curl \
        software-properties-common

2.使用dockerEE客户端的地址添加官方GPG密钥

    $ curl -fsSL <DOCKER-EE-URL>/gpg | sudo apt-key add -
    
3.认证密钥指纹是：`DD91 1E99 5A64 A202 E859 07D6 BC14 F10B 6D08 5F96`

    $ apt-key fingerprint 0EBFCD88
         pub   4096R/6D085F96 2017-02-22
             Key fingerprint = DD91 1E99 5A64 A202 E859  07D6 BC14 F10B 6D08 5F96
         uid       [ultimate] Docker Release (EE deb) <docker@docker.com>
         sub   4096R/91A29FA3 2017-02-22
         
4.使用下面的地址来设置stable仓库，使用你在先决条件注意下面的url地址替代你的Docker-EE-URL

注意：这个命令`lsb_release -cs`返回的是Ubuntu分布式系统的名字，例如：`xenial`

    $ sudo add-apt-repository \
        "deb [arch=amd64] <DOCKER-EE-URL> \
        $(lsb_release -cs) \
        stable-17.03"
        
###### 正式安装docker

1、更新apt

   `sudo apt-get update`
   
2.安装最新版本的docker或者安装指定版本的docker。使用下面的命令安装最新版本的docker

DockerCE的安装命令:     
      	
    sudo apt-get install docker-ce
       
DockerEE的安装命令:

    sudo apt-get install docker-ee
注意：如果有多个仓库能用，在执行apt-get install和apt-get update命令时没有指定docker的版本那么默认安装的版本是docker的最新版本。

3.在生产环境上，如果你安装指定版本的docker来代替最新版本的docker，输出将会被截断，接而列出所有的可用版本，DockerEE的客户端上可以看到DockerCE

    $ apt-cache madison docker-ce
    docker-ce | 17.03.0~ce-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages

4.通过运行hello world镜像来查看DockerEE或者DockerCE是不是安装正确

    $ sudo docker run hello-world
这个命令会下载一个test镜像并且将该镜像运行在容器中，当容器运行时，他会打印信息和退出

Docker的安装和运行需要使用root用户的权限才能操作，这样安装后允许非特权的docker用户能够运行docker命令并且可以配置其他的配置项。

5、升级Docker
想要升级Docker，首先你需要执行命令`sudo apt-get update`, 接着安装设备，选择你所需要的版本的Docker来安装。

6、从包中安装
如果你不想通过仓库来安装Docker，那么你可以通过在下`.deb`文件来手动地安装Docker，如果你想更新Docker，你每次都需要下载一个新文件来手动地更新Docker。

1）、这一步对于DockerCE和DockerEE来说是不同的
 DockerCE:去这个网站： https://download.docker.com/linux/ubuntu/dists/； 选中你的Ubuntu版本，浏览`stable/pool/stable/amd64/`;选择与你的Ubuntu版本对应下的`.deb`版本的文件。
 
   注意：如果想要安装edge版本的包，把`stable/pool/stable/amd64/`改为`edge/pool/stable/amd64/`。
 
 DockerEE：同样是去相应的网站下载相关的包，`x86_64/stable-17.03`,
 
 2）、安装Docker，把下面的`path`改变为你下载Docker包的地址。
 
     $ sudo dpkg -i /path/to/package.deb
     
 Docker守护进程就会自动启动起来。
 
 3）、通过运行hello world镜像来查看DockerEE或者DockerCE是不是安装正确

     $ sudo docker run hello-world
     
     
 这个命令会下载一个test镜像并且将该镜像运行在容器中，当容器运行时，他会打印信息和退出

Docker的安装和运行需要使用root用户的权限才能操作，这样安装后允许非特权的docker用户能够运行docker命令并且可以配置其他的配置项。

4）、升级Docker
想要升级Docker，首先你需要执行命令`sudo apt-get update`, 接着安装设备，选择你所需要的版本的Docker来安装。

5）、从包中安装
如果你不想通过仓库来安装Docker，那么你可以通过在下`.deb`文件来手动地安装Docker，如果你想更新Docker，你每次都需要下载一个新文件来手动地更新Docker。

7、卸载Docker

1）、卸载Docker包

    DockerCE：sudo apt-get purge docker-ce
    DockerEE：sudo apt-get purge docker-ee
    
2）、你主机上的镜像、容器、数据卷和自定义配置文件是不会自动移除的，删除所有的镜像、容器和数据卷，你需要使用下面的命令

     sudo rm -rf /var/lib/docker
     
 
#### 2、在Red Hat Enterprise下安装docker
要想在红帽子上安装Docker，确信你满足前提条件，然后在安装Docker

##### 2.1、先决条件

##### 2.1.1、DockerEE仓库的URL
为了安装企业版本的Docker，你需要明白你DockerEE的URL与你的试验和签署联系到一起，下面是获取这些信息的途径和方法。
1、输入这个URL地址进入这个网站: `https://store.docker.com/?overlay=subscriptions`。
2、在`Docker Enterprise Edition for Ubuntu`部分中的里面选择 `Get Details/Setup Instructions`这两项。
3、从域区域中拷贝，点击这个即可：`Copy and paste this URL to download your Edition`。
当你看到站位文本为`<DOCKER-EE-URL>`使用URL地址，要学习更多关于Docker EE的东西，看这个`Docker Enterprise Edition`部分的内容。
DockerCE不能再Redhat上使用

###### 系统要满足的条件
为了安装Docker，你需要是RHEL7版本的64位的Redhat操作系统。

###### 卸载老版本的Docker

老版本的Docker也称为`docker`或者`docker-engine`，如果安装了这些，卸载他们和卸载他们的依赖项

     $ sudo yum remove docker \
                       docker-common \
                       container-selinux \
                       docker-selinux \
                       docker-engine
                       
如果yum报告这些包没有一个被安装那么就是OK的啦。

`/var/lib/docker/`的内容，包括镜像，容器、数据卷和网络都被保留，DockerEE包现在被称为`docker-ee`

#####  安装DockerEE
你可以根据你的需求按照不同的方式来安装DockerEE
大多数用户通过配置Docker仓库的方式来安装Docker，这样可以减少一些安装和升级的任务，这是官方比较推荐的方法(其实，官方挺喜欢这样的搞，因为你可以经常用他的软件了)。

许多用户下载RPM包手动地安装Docker和完全手动管理docker的升级，这是一个很好的方案例如一些有缺陷的系统不用连接网络也能安装Docker。

###### 通过仓库来安装
在你首次在一台新主机上安装docker之前，你需要配置docker仓库，接下来你才通过仓库来安装和更新docker，
1、配置docker仓库
   从`/etc/yum.repos.d/`移除已经存在的Docker仓库
2、在`/etc/yum/vars/`里面存储两个变量
   在这里面`/etc/yum/vars/dockerurl`存储EE的地址，把这项`<DOCKER-EE-URL>`替换成你在先决条件的中的URL地址，
   
       $ sudo sh -c 'echo "<DOCKER-EE-URL>" > /etc/yum/vars/dockerurl'
       
3、在这`/etc/yum/vars/dockerosversion`里面存储RHEL版本的字符串，从面的表中获取恰当的值，大多数用户使用7，

图片18:
    ![图片18](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/18.png  "图片18")
    
         $ sudo sh -c 'echo "<VERSION-STRING>" > /etc/yum/vars/dockerosversion'
         
         
4、安装提供了`yum-config-manager`这个功能的`yum-utils`

    $ sudo yum install -y yum-utils
    
5、使用下面的命令来增加`stable `仓库

    $ sudo yum-config-manager \
       --add-repo \
       <DOCKER-EE-URL>/docker-ee.repo
       
###### 安装Docker
1、更新`yum`包

    $ sudo yum makecache fast
    
如果第一时间你刷新了包的索引，这样会增加Docker仓库，也将会促使你接受GPG密钥，并且密钥的指纹将会被显示认证指纹匹配`DD91 1E99 5A64 A202 E859 07D6 BC14 F10B 6D08 5F96`,如果发生这样的事，请你接密钥。

2、安装最新版本的Docker或者去`next step`中安装指定版本的Docker
 
    $ sudo yum -y install docker-ee
    
3、在生产环境上，你可以安装指定版本的Docker来替代最新版本的Docker，使用`sort -r`按版本号从高到底的顺序列出所有可以使用的docker版本，并且使截断输出的。
注意: yum list这个命令仅仅显示二进制包，为了显示源包，从包名中省略`.x86_64 `。

    $ yum list docker-ee.x86_64  --showduplicates |sort -r

    docker-ee.x86_64  17.03.0.el7                               docker-ee-stable   
列出的内容依赖于能够使用的的仓库和指定的RHEL版本，选择一个指定的版本来安装，第二列是版本字符串，第三列是仓库的名字，安装指定的版本，添加版本号到包名并且通过连字符来分离他们

     $ sudo yum -y install docker-ee-<VERSION_STRING>
     
4、启动docker

     $ sudo systemctl start docker
     
5、通过运行hello world镜像来查看检验Docker是不是安装正确

     $ sudo docker run hello-world
     
这个命令会下载一个test镜像并且将该镜像运行在容器中，当容器运行时，他会打印信息和退出
Docker的安装和运行需要使用root用户的权限才能操作，这样安装后允许非特权的docker用户能够运行docker命令并且可以配置其他的配置项。

###### 升级DockerEE

想要升级DockerEE，首先运行着个命令`sudo yum makecache fast`，然后接下来安装设备，选择新的你想要安装的Docker。

###### 安装包
如果你不使用官方的Docker仓库来安装Docker，你可以下载发布的`.rpm`文件来手动地安装你的Docker，如果你想要升级Docker，每次你都得下载一个新的文件。

1、去你浏览中尝试和签署的与DockerEE有联系的URL地址下，然后去`7/x86_64/stable-17.03/Packages`根据你要安装的Docker的版本下载`.rpm`文件。

2、安装Docker，把下面的`path`改变为你下载Docker包的地址。
 
     $ sudo yum install /path/to/package.rpm
     
3、启动Docker
    
    $ sudo systemctl start docker
 
4、通过运行hello world镜像来查看DockerEE或者DockerCE是不是安装正确

     $ sudo docker run hello-world
     
这个命令会下载一个test镜像并且将该镜像运行在容器中，当容器运行时，他会打印信息和退出
Docker的安装和运行需要使用root用户的权限才能操作，这样安装后允许非特权的docker用户能够运行docker命令并且可以配置其他的配置项。

###### 升级DockerEE

为了升级Docker，下载新的文件包并且重新安装程序，使用这个命令`yum -y upgrade`来替代这个命令`yum -y install`,并且指向新的文件

###### 卸载DockerEE
1、卸载DockerEE包

    $ sudo yum -y remove docker-ee
    
2、在你主机上的镜像、容器、数据卷和自定义的文件不会自动移除，为了删除所有的容器、镜像和数据卷，使用下面的命令
 
    $ sudo rm -rf /var/lib/docker

你必须手动地删除一些编辑的配置文件。

#### 3、在CentOS下安装docker
如果想要在CentOS上安装Dockers，确信你已近满足先决条件，再安装Dockers

##### 3.1.先决条件

######  DockerEE客户端
为了安装企业版本的Docker，你需要明白你DockerEE的URL与你的试验和签署联系到一起，下面是获取这些信息的途径和方法。
1、输入这个URL地址进入这个网站: `https://store.docker.com/?overlay=subscriptions`。
2、在`Docker Enterprise Edition for Ubuntu`部分中的里面选择 `Get Details/Setup Instructions`这两项。
3、从域区域中拷贝，点击这个即可：`Copy and paste this URL to download your Edition`。
当你看到站位文本为`<DOCKER-EE-URL>`使用URL地址，要学习更多关于Docker EE的东西，看这个`Docker Enterprise Edition`部分的内容。
DockerCE不能再Redhat上使用

###### 系统需求
想要更好地安装Docker，你需要64位的CentOS 7版本的CentOS系统.

###### 卸载老版本的Docker

老版本的Docker也称为`docker`或者`docker-engine`，如果安装了这些，卸载他们和卸载他们的依赖项

     $ sudo yum remove docker \
                  docker-common \
                  container-selinux \
                  docker-selinux \
                  docker-engine
                       
如果yum报告这些包没有一个被安装那么就是OK的啦。

`/var/lib/docker/`的内容，包括镜像，容器、数据卷和网络都被保留，DockerEE包现在被称为`docker-ee`

###### 使用 yum 安装

执行以下命令安装依赖包：

```bash
$ sudo yum install -y yum-utils \
           device-mapper-persistent-data \
           lvm2
```

鉴于国内网络问题，强烈建议使用国内源，官方源请在注释中查看。

执行下面的命令添加 `yum` 软件源：

```bash
$ sudo yum-config-manager \
    --add-repo \
    https://mirrors.ustc.edu.cn/docker-ce/linux/centos/docker-ce.repo


# 官方源
# $ sudo yum-config-manager \
#     --add-repo \
#     https://download.docker.com/linux/centos/docker-ce.repo    
```

如果需要最新版本的 Docker CE 请使用以下命令：

```bash
$ sudo yum-config-manager --enable docker-ce-edge
```

如果需要测试版本的 Docker CE 请使用以下命令：

```bash
$ sudo yum-config-manager --enable docker-ce-test
```

###### 安装 Docker CE

更新 `yum` 软件源缓存，并安装 `docker-ce`。

```bash
$ sudo yum makecache fast
$ sudo yum install docker-ce
```

###### 使用脚本自动安装

在测试或开发环境中 Docker 官方为了简化安装流程，提供了一套便捷的安装脚本，CentOS 系统上可以使用这套脚本安装：

```bash
$ curl -fsSL get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh --mirror Aliyun
```

执行这个命令后，脚本就会自动的将一切准备工作做好，并且把 Docker CE 的 Edge 版本安装在系统中。

###### 启动 Docker CE

```bash
$ sudo systemctl enable docker
$ sudo systemctl start docker
```

###### 建立 docker 用户组

默认情况下，`docker` 命令会使用 [Unix socket](https://en.wikipedia.org/wiki/Unix_domain_socket) 与 Docker 引擎通讯。而只有 `root` 用户和 `docker` 组的用户才可以访问 Docker 引擎的 Unix socket。出于安全考虑，一般 Linux 系统上不会直接使用 `root` 用户。因此，更好地做法是将需要使用 `docker` 的用户加入 `docker` 用户组。

建立 `docker` 组：

```bash
$ sudo groupadd docker
```

将当前用户加入 `docker` 组：

```bash
$ sudo usermod -aG docker $USER
```

退出当前终端并重新登录，进行如下测试。

###### 测试 Docker 是否安装正确

```bash
$ docker run hello-world

Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
ca4f61b1923c: Pull complete
Digest: sha256:be0cd392e45be79ffeffa6b05338b98ebb16c87b255f48e297ec7f98e123905c
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://cloud.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/
```

若能正常输出以上信息，则说明安装成功。

###### 添加内核参数

默认配置下，如果在 CentOS 使用 Docker CE 看到下面的这些警告信息：

```bash
WARNING: bridge-nf-call-iptables is disabled
WARNING: bridge-nf-call-ip6tables is disabled
```

请添加内核配置参数以启用这些功能。

```bash
$ sudo tee -a /etc/sysctl.conf <<-EOF
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
EOF
```

然后重新加载 `sysctl.conf` 即可

```bash
$ sudo sysctl -p
```

#### 3、在Fedora下安装docker
要在Fedora下面安装Docker,确保你满足下面的先决条件，然后再安装Docker。

##### 先决条件
DockerEE客户端：
DockerEE不支持Fedora平台，

##### 系统满足的条件
为了安装Dockers，你需要64位的Fedora下面这些版本中的一个：
- 24
- 25

##### 卸载老版本的Docker
老版本的Dockers称为docker或者docker-engine，如果你安装了他们，想要卸载Docker，使用下面的命令

    $ sudo dnf remove docker \
                     docker-common \
                     container-selinux \
                     docker-selinux \
                     docker-engine
                     
如果dnf报告这些包没有一个被安装，那么久OK了。
`/var/lib/docker/`的内容是被隐藏的，里面包含了镜像，容器，数据券和网络；DockerCE包现在被称为docker-ce。
 
 ##### 安装DockerCE
 
你可以根据你的需求用不同的方式来安装DockerCE：
- 大多数用户通过配置docker仓库来安装docker，这样做的优点是每一次安装和更新任务都是轻松的。这也是官方比较推荐的方法。
- 一些用户下载PRM包手动地安装docker并且升级的时候也是完全手动的。这是在没有和外界网络连接的主机上安装docker的有效方法

###### 安装使用仓库
在你在你的新主机上第一次安装docker之前，你需要配置docker仓库，以后你就可以通过仓库来安装和更新docker，
 
###### 配置docker仓库
安装提供命令管理DNF仓库的`dnf-plugins-core`包

    $ sudo dnf -y install dnf-plugins-core
使用下面的命令配置stable仓库，你总是需要stable容器，即使你也想过安装edge仓库

    $ sudo dnf config-manager \
        --add-repo \
        https://download.docker.com/linux/fedora/docker-ce.repo

可选择的：能用的边缘仓库，这个仓库包含在docker.repo上但是默认是不能用的，你可以在stable仓库变使它变得可用

    $ sudo dnf config-manager --set-enabled docker-ce-edge
    
你可以通过运行DNF带有--disable flag的配置管理命令来是edge仓库不能用，下面这条命令是使edge仓库不能被使用的命令

    $ sudo dnf config-manager --set-disabled docker-ce-edge

##### 通过命令行安装dockerCE
1.安装最新版本的DockerCE,也可以安装指定版本的Docker

    $ sudo dnf install docker-ce
    
如果这是您第一次从最近添加的存储库安装软件包，系统会提示您接受GPG密钥，并显示密钥的指纹。 确认指纹是否与060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35匹配，如果是，请接受密钥。

有多个Docker存储库？

如果启用了多个Docker存储库，则在未指定dnf install或dnf update命令中的版本的情况下安装或更新将始终安装尽可能高的版本，这可能不适合您的稳定性需求。

2.在生产系统上，您应该安装特定版本的Docker CE，而不是始终使用最新版本。 列出可用的版本。 此示例使用sort -r命令将结果按版本号排序，从最高到最低并被截断。

    $ dnf list docker-ce  --showduplicates | sort -r
    docker-ce.x86_64  17.12.0.fc26  docker-ce-stable

列表的内容取决于启用了哪些存储库，并且特定于您的Fedora版本（在此示例中，由版本中的.fc26后缀指示）。 选择一个特定的版本进行安装。 第二列是版本字符串。 第三列是存储库名称，它指示软件包来自哪个存储库并且通过扩展其稳定性级别。 要安装特定版本，请将版本字符串附加到包名称并用连字符（ - ）分隔：

    $ sudo dnf -y install docker-ce-<VERSION>

3.启动Docker
   
    $ sudo systemctl start docker
    
4.通过运行hello-world映像验证Docker CE是否已正确安装。

    $ sudo docker run hello-world
    
该命令下载测试图像并将其运行到容器中。 当容器运行时，它会打印一条信息消息并退出。

Docker CE已安装并正在运行。 您需要使用sudo来运行Docker命令。 继续Linux postinstall以允许非特权用户运行Docker命令以及其他可选配置步骤。

###### 升级DOCKER CE

要升级Docker CE，请按照安装说明进行操作，选择要安装的新版本。

##### 通过包安装Docker

如果您无法使用Docker的存储库来安装Docker，则可以下载用于发布的.rpm文件并手动安装。 每次要升级Docker CE时，都需要下载一个新文件。

1.去`https://download.docker.com/linux/fedora/`并选择您的Fedora版本。 转到`x86_64/stable/Packages/`并下载要安装的Docker版本的.rpm文件。
注：要安装edge包，请将上述URL中的stable字改为edge。

2.安装Docker CE，将下面的路径更改为您下载Docker软件包的路径。

    $ sudo dnf -y install /path/to/package.rpm
3.启动Docker

    $ sudo systemctl start docker
4.通过运行hello-world映像验证Docker CE是否已正确安装。

    $ sudo docker run hello-world
    
该命令下载测试图像并将其运行到容器中。 当容器运行时，它会打印一条信息消息并退出。

Docker CE已安装并正在运行。 您需要使用sudo来运行Docker命令。 继续执行Linux的安装后步骤，以允许非特权用户运行Docker命令以及其他可选配置步骤。

###### 升级DOCKER CE

要升级Docker CE，请下载较新的软件包文件并重复安装过程，使用dnf -y upgrade而不是dnf -y install，然后指向新文件。

##### 使用便捷脚本进行安装
Docker在get.docker.com和test.docker.com上提供了便捷脚本，用于快速非交互式地将Docker CE的边缘和测试版本安装到开发环境中。 这些脚本的源代码位于docker-install存储库中。 不建议在生产环境中使用这些脚本，并且在使用它们之前应了解潜在风险

1.脚本需要root或sudo权限才能运行。 因此，在运行脚本之前，应仔细检查和审核脚本。
2.这些脚本会尝试检测您的Linux发行版和版本，并为您配置您的软件包管理系统。 另外，这些脚本不允许您自定义任何安装参数。 这可能会导致不支持的配置，无论是从Docker的角度还是从您自己的组织准则和标准。
3.这些脚本会安装包管理器的所有依赖关系和建议，而不要求确认。 这可能会安装大量的包，具体取决于主机的当前配置。
4.该脚本不提供指定要安装哪个版本的Docker的选项，并安装在“边缘”通道中发布的最新版本。
5.如果Docker已经使用其他机制安装在主机上，请不要使用便捷脚本。

本示例使用get.docker.com上的脚本在Linux上安装Docker CE的最新版本。 要安装最新的测试版本，请改用test.docker.com。 在下面的每个命令中，将每个出现的get替换为test。

    $ curl -fsSL get.docker.com -o get-docker.sh
    $ sudo sh get-docker.sh

    <output truncated>

    If you would like to use Docker as a non-root user, you should now consider
    adding your user to the "docker" group with something like:

      sudo usermod -aG docker your-user

    Remember to log out and back in for this to take effect!

    WARNING: Adding a user to the "docker" group grants the ability to run
             containers which can be used to obtain root privileges on the
             docker host.
             Refer to https://docs.docker.com/engine/security/security/#docker-daemon-attack-surface
             for more information.
             
Docker CE已安装。 它在基于DEB的发行版上自动启动。 在基于RPM的分发上，您需要使用适当的systemctl或service命令手动启动它。 如消息所示，非root用户默认情况下不能运行Docker命令。

###### 升级后使用便利脚本后的DOCKER
如果您使用便捷脚本安装Docker，则应直接使用软件包管理器升级Docker。 重新运行便捷脚本没有任何优势，如果它试图重新添加已添加到主机的存储库，则会产生问题。

##### 卸载Docker
1.卸载Docker包

    $ sudo dnf remove docker-ce

 2.不会自动删除主机上的图像，容器，卷或自定义配置文件。 删除所有图像，容器和卷：
 
    $ sudo rm -rf /var/lib/docker

您必须手动删除任何已编辑的配置文件。
 
## 第三章：Docke的使用
本章分为三个部分，第一部分：docker的启动，第二部分:docker的使用案例学习；第三部分：docker总览。在第一大部分中共6个小节；1.适配与设置；2.容器；3.服务；4.集群；5.进程栈的应用；6.部署应用。

### 第一节:docker的启动
在这一节中，我们将讲解：1.适配与设置；2.容器；3.服务；4.集群；5.进程栈的应用；6.部署应用。经过这小节的学习，你将能学到一下东西。
1).docker的设置与导向
2).构建你自己的第一个应用程序
3).将你的应用程序做成一个缩放的服务
4).多台物理机部署你的应用程序
5).添加一个可视化的逆向的数据
6).部署生产环境上的集群服务

这个应用程序非常简单，所以你不用花太多的心思在代码怎么实现上。毕竟，docker的价值是怎么去创建，运送和运行应用程序，因此，要把你的应用程序看成是完全不知道实际要做些什么。

#### 1.先决条件
在开始之前，为了理解什么是docker和为什么使用docker，我们将定义一些预知的概念。在开始之前，假设你对下面的概念已经清晰理解
1) ip地址和端口号
2) 虚拟机
3) 编辑配置文件
4) 理解代码的依赖与创建
5) 机器使用的一些前提条件；如：CPU的百分比，ARM的字节使用等等。

#### 2.容器的简介
* 镜像是包含软件运行的所需要的所有物理固件，包括代码，运行日志，库，环境变量与配置文件等的一个轻量级的，单一的可执行文件包。
* 容器是镜像运行时的一个实例，即软件运行时在内存中运行的镜像，它运行完全与默认的主机环境相关,仅仅只能通过主机的host文件去配置它。
* 容器在本地主机上运行应用程序，仅通过虚拟层进入虚拟机资源docker容器的性能比虚拟机的性能高，容器能够本地进入，每一个不连续运行的进程，不会像其他程序一样占用很多的内存。

#### 3.容器与虚拟机
容器与虚拟机的图标比较

##### 虚拟机图解

图片31： 
    ![图片31](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/QQ%E6%88%AA%E5%9B%BE20170825181106.png  "图片31")

虚拟机运行在客户机操作系统上-每个盒子中的OS层，资源是密集的，

Virtual machines run guest operating systems—note the OS layer in each box. This is resource intensive, and the resulting disk image and application state is an entanglement of OS settings, system-installed dependencies, OS security patches, and other easy-to-lose, hard-to-replicate ephemera.


#### 容器图解

图片32:
   ![图片32](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/QQ%E6%88%AA%E5%9B%BE20170825181124.png  "图片32") 

#### 准备你的Docker环境

在支持Docker的平台上安装维护Docker社区版或者安装维护Docker企业版，安装Docker的步骤请参见第一章。

#### 测试docker版本
请确保你的设备上安装好能使用的Docker
    
命令行：`docker --version`
 
    guosjdeMacBook:~ guo$ docker --version
    Docker version 17.09.0-ce, build afdb6d4
    guosjdeMacBook:~ guo$
    
 运行`docker version`(没有--)或者`docker info`查看关于你安装的Docker的更详细的信息。如下：
 
 
 运行`docker version`(没有--)或者`docker info`查看关于你安装的Docker的更详细的信息。如下
 
    guosjdeMacBook:~ guo$ docker version
    Client:
     Version:      17.09.0-ce
     API version:  1.32
     Go version:   go1.8.3
     Git commit:   afdb6d4
     Built:        Tue Sep 26 22:40:09 2017
     OS/Arch:      darwin/amd64

    Server:
     Version:      17.09.0-ce
     API version:  1.32 (minimum version 1.12)
     Go version:   go1.8.3
     Git commit:   afdb6d4
     Built:        Tue Sep 26 22:45:38 2017
     OS/Arch:      linux/amd64
     Experimental: true
    guosjdeMacBook:~ guo$
    
    
    guosjdeMacBook:~ guo$ docker info
    Containers: 2
     Running: 0
     Paused: 0
     Stopped: 2
    Images: 2
    Server Version: 17.09.0-ce
    Storage Driver: overlay2
     Backing Filesystem: extfs
     Supports d_type: true
     Native Overlay Diff: true
    Logging Driver: json-file
    Cgroup Driver: cgroupfs
    Plugins:
     Volume: local
     Network: bridge host ipvlan macvlan null overlay
     Log: awslogs fluentd gcplogs gelf journald json-file logentries splunk syslog
    Swarm: inactive
    Runtimes: runc
    Default Runtime: runc
    Init Binary: docker-init
    containerd version: 06b9cb35161009dcb7123345749fef02f7cea8e0
    runc version: 3f2f8b84a77f73d38244dd690525642a72156c64
    init version: 949e6fa
    Security Options:
     seccomp
      Profile: default
    Kernel Version: 4.9.49-moby
    Operating System: Alpine Linux v3.5
    OSType: linux
    Architecture: x86_64
    CPUs: 2
    Total Memory: 1.952GiB
    Name: moby
    ID: SJ5J:F7GW:46UT:FCIR:SPFW:VRDL:3AUM:JLU3:CI2E:GT2R:I42K:AJ7Y
    Docker Root Dir: /var/lib/docker
    Debug Mode (client): false
    Debug Mode (server): true
     File Descriptors: 18
     Goroutines: 29
     System Time: 2018-02-12T01:28:52.285678754Z
     EventsListeners: 1
    No Proxy: *.local, 169.254/16
    Registry: https://index.docker.io/v1/
    Experimental: true
    Insecure Registries:
     127.0.0.0/8
    Live Restore Enabled: false

    guosjdeMacBook:~ guo$
    
注意：为避免权限错误，请添加您的用户到docker组，或者使用超级用户权限

#### 测试Docker的安装

通过运行一个简单的hello world镜像来测试你的安装
命令行：`docker run hello-world`

    guosjdeMacBook:~ guo$ docker run hello-world
    Hello from Docker!
    This message shows that your installation appears to be working correctly.

    To generate this message, Docker took the following steps:
     1. The Docker client contacted the Docker daemon.
     2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
        (amd64)
     3. The Docker daemon created a new container from that image which runs the
        executable that produces the output you are currently reading.
     4. The Docker daemon streamed that output to the Docker client, which sent it
        to your terminal.

    To try something more ambitious, you can run an Ubuntu container with:
     $ docker run -it ubuntu bash

    Share images, automate workflows, and more with a free Docker ID:
     https://cloud.docker.com/

    For more examples and ideas, visit:
     https://docs.docker.com/engine/userguide/

    guosjdeMacBook:~ guo$

注意：如果你是新安装的docker，正常情况下是没有镜像的，当你运行docker run + 镜像名字的时候，docker会自动去下载官方镜像；当hello-world镜像下载到你的设备上时，使用`docker images ls`可以列出所有镜像，下面是我的设备上的可以列出的镜像：

    guosjdeMacBook:~ guo$ docker images ls
    REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
    guosjdeMacBook:~ guo$ docker image ls
    REPOSITORY                                                TAG                 IMAGE ID            CREATED             SIZE
    hello-world                                               latest              f2a91732366c        2 months ago        1.85kB
    registry.cn-hangzhou.aliyuncs.com/denverdino/tensorflow   latest              df6e19313fd7        5 months ago        1.21GB
    kaixhin/theano                                            latest              b2f646041184        6 months ago        634MB
    guosjdeMacBook:~ guo$
    
列出容器（通过那个镜像产生的容器），如果镜像一直运行着，那么你不可以使用`-- all`选项：

    guosjdeMacBook:~ guo$ docker container ls --all
    CONTAINER ID        IMAGE                                                     COMMAND             CREATED             STATUS                      PORTS                NAMES
    c58dec734321        hello-world                                               "/hello"            11 minutes ago      Exited (0) 11 minutes ago                        hungry_nightingale
    c3bcd1d52eb1        hello-world                                               "/hello"            11 minutes ago      Exited (0) 11 minutes ago                        quirky_clarke
    3cb3f43adae6        hello-world                                               "/hello"            11 minutes ago      Exited (0) 11 minutes ago                        gifted_montalcini
    d362e8fe6bdb        kaixhin/theano                                            "/bin/bash"         2 months ago        Exited (255) 2 months ago                        cranky_snyder
    3b77a144a920        registry.cn-hangzhou.aliyuncs.com/denverdino/tensorflow   "/bin/bash"         2 months ago        Exited (255) 2 months ago   6006/tcp, 8888/tcp   dreamy_perlman
    guosjdeMacBook:~ guo$

#### 本部分命令行总结

##### List Docker CLI commands
docker
docker container --help

##### 显示docker的版本或者信息
docker --version
docker version
docker info

##### 运行docker镜像
docker run hello-world

##### 列出docker镜像
docker image ls

##### 列出docker容器（-all参数，-a -q参数）
docker container ls
docker container ls -all
docker container ls -a -q

#### 第一部分总结

容器化使得能够CI/CD无缝结合，列如：
1.应用程序不再依赖系统
2.更新能够推送一部分分布应用
3.资源的密度能够得到优化
也就是说，使用Docker,不在使用重量级虚拟主机，也能使得你的应用程序快速部署执行。

### 第二节.容器

#### 1.先决条件
1）安装1.13版本或者更高版本的Docker
2）请阅读本章第一节
3）给你安装好的环境做一个快速测试并确保你的所有的配置已经配置好
`docker run hello-world`

#### 2.容器的介绍
是时候使用docker的方式构建一个应用程序了，我们在容器中的栈应用层级的底层开始构建这样一个应用程序，将会在这节里面介绍；后面将会介绍到，这个层级定义容器在生成环境上怎么的服务将在第三章中做介绍。最后，在栈应用的顶层，定义了所有服务之间是怎么交互的，这将在第五部分中介绍。

* 栈
* 服务
* 容器（本节介绍）

#### 3.新的开发环境

在以前，如果你写一个Python程序，首先要做的第一件事就是在你的设备上安装Python，然后在你的机器上运行Python。但是，当你在你机器上构建环境时，你需要考虑你所构建的环境能够让你的应用程序能够执行，而且必须和你的生成环境一致。

使用Docker，你仅仅只需要摄取便捷式的Python运行镜像，不需要安装必要的Python环境。然后，你就可以构建自己的包含Python基础镜像的应用程序了，它能够确保应用程序的依赖和运行。

这些便捷式的镜像被定义在一个叫做dockerfile的文件中

#### 4.使用Dockerfile文件定义一个容器

Dockerfile文件中定义了你环境上的容器内部是怎么运行的。可访问资源如网络和硬盘驱动在这个环境中是虚拟化的，它与你的系统息息相关，因此，你需要映射端口到外部网络，并且需要制定什么文件你想要”拷入“环境中。当然，做完之后，你在Dockerfile中按你的想法构建无论什么环境都能运行的应用程序。

##### 5.DockerFile
创建一个空的目录，使用`cd`命令进入新目录中，创建一个名叫dockerfile的文件，拷贝复制下面的内容到文件中并且保存它。在心的dockerfile文件中写下注释与解释。

    # Use an official Python runtime as a parent image
    FROM python:2.7-slim

    # Set the working directory to /app
    WORKDIR /app

    # Copy the current directory contents into the container at /app
    ADD . /app

    # Install any needed packages specified in requirements.txt
    RUN pip install --trusted-host pypi.python.org -r requirements.txt

    # Make port 80 available to the world outside this container
    EXPOSE 80

    # Define environment variable
    ENV NAME World

    # Run app.py when the container launches
    CMD ["python", "app.py"]
    
##### 1）在代理服务器的后面？
一旦web程序运行，代理服务器能够锁定并连接到web应用程序。如果你在代理服务器的后面，添加下面内容到Dockerfile文件，使用ENV命令行为你的代理服务器指定主机和端口号：

    # Set proxy server, replace host:port with values for your servers
    ENV http_proxy host:port
    ENV https_proxy host:port
    
在这些线之前称之为 `pip`,这样使得安装能够成功。

这个Dockerfile文件涉及到一对没有创建的文件，名叫app.py和requirements.txt。接下来我们创建他们：

##### 2）应用程序自己创建
创建两个或者更多文件，requirement.txt和app.py,接着使用dockerfile将他们放到同意文件夹下面。这就完成了应用程序的创建，是不是看起来很简单。当上面的Dockerfile被创建如镜像时，由于Dockerfile中添加了命令行，app.py和requirements.txt是会被呈现的。因为EXPOSE命令行外部通过app.py是可以访问HTTP服务的。

###### requirements.txt

    Flask
    Redis 
    
###### app.py


    from flask import Flask
    from redis import Redis, RedisError
    import os
    import socket

    # Connect to Redis
    redis = Redis(host="redis", db=0, socket_connect_timeout=2, socket_timeout=2)

    app = Flask(__name__)

    @app.route("/")
    def hello():
        try:
            visits = redis.incr("counter")
        except RedisError:
            visits = "<i>cannot connect to Redis, counter disabled</i>"

        html = "<h3>Hello {name}!</h3>" \
               "<b>Hostname:</b> {hostname}<br/>" \
               "<b>Visits:</b> {visits}"
        return html.format(name=os.getenv("NAME", "world"), hostname=socket.gethostname(), visits=visits)

    if __name__ == "__main__":
        app.run(host='0.0.0.0', port=80)

现在我们可以使用`pip install -r requirements.txt`安装为Python程序安装FLask和Redis库，应用程序将打印环境变量，也会调用socket.gethosname()来输出主机名字。最终，因为Redis并没有运行（原因是我们只安装了Python库，没有让Redis自己安装），我们应该尝试在这里使用失败的时候打印错误信息。

注意：当内部的容器检索容器ID时进入主机名字，就像可执行程序运行时的进程ID

是的，在你的系统上你不需要Python或者requirements.txt文件中的其他东西，你就可在你的系统上运行镜像安装他们。这似乎也不需要你去配置Python和Flask的环境，但是你得配置。

#### 3）构建自己的应用程序
我们准备好构建自己的应用程序了，确保你的新目录仍然在栈的最顶层，`ls`这个命令可以直观的看到

    $ ls
    Dockerfile		app.py			requirements.txt
现在运行构建命令，这将会创建一个Docker镜像，使用-t参数会有一个友好的名字

    docker build -t friendlyhello .
    
想要知道你构建的镜像在哪吗?时时上他就在你本机的本地Docker仓库

    $ docker image ls

    REPOSITORY            TAG                 IMAGE ID
    friendlyhello         latest              326387cea398

#### 4.运行你的应用程序

运行应用程序，将你机器的4000端口映射到容器的公共80端口，使用-p参数

    docker run -p 4000:80 friendlyhello
    
你应该通过`http://0.0.0.0:80`看你Python服务的信息。那些信息来自你内部容器，容器并不知道你把80端口映射到容器的4000端口，正确的URL地址是`http://localhost:4000`。

把URL地址输入到浏览器中可以在web页面上可以看到服务器的信息。

图片20： 
    ![图片20](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/20.png  "图片20")

注意：如果你在Win7上使用Docker ToolBox,请使用Docker虚机IP代替localhost。如：`http://192.168.99.100:4000/`。可以使用`docker-machine IP
`命令查看IP地址.

当然，你也可以使用curl命令行来查看相同的内容

    $ curl http://localhost:4000

    <h3>Hello World!</h3><b>Hostname:</b> 8fc990912a14<br/><b>Visits:</b> <i>cannot connect to Redis, counter disabled</i>

这个4000：80的端口重映射是为了演示Dockerfile中的EXPOSE与使用docker run -p发布的内容之间的区别。 在后面的步骤中，我们只需将主机上的端口80映射到容器中的端口80并使用http//localhost。

按control + c键终止退出

##### 在Windows上，显式停止容器

在Windows系统上，CTRL + C不会停止容器。 因此，首先键入CTRL + C以获取提示（或打开另一个shell），然后键入`docker container ls`列出正在运行的容器，然后按`docker container stop <Container NAME或ID>`停止容器。 否则，当您尝试在下一步中重新运行容器时，会从守护程序中收到错误响应。

现在让我们使用独立模式在后台运行应用程序

    docker run -d -p 4000:80 friendlyhello

您可以获取应用的长容器ID，然后将其踢回到终端。 您的容器正在后台运行。 您还可以使用docker container ls查看缩写的容器ID（并且在运行命令时都可以互换使用）：

    $ docker container ls
    CONTAINER ID        IMAGE               COMMAND             CREATED
    1fa4ab2cf395        friendlyhello       "python app.py"     28 seconds ago
    
请注意，容器ID与`http//localhost4000`上的内容匹配。

现在使用docker container stop来结束进程，使用CONTAINER ID，如下所示：

    docker container stop 1fa4ab2cf395

#### 5.共享你的镜像

为了演示我们刚才创建的可移植性，我们上传我们构建的镜像并在其他地方运行它。 毕竟，当您想要将容器部署到生产环境时，您需要知道如何推送注册表。

注册表是仓库的集合，而仓库是镜像的集合 - 有点像GitHub仓库，但代码已经创建。 注册表上的帐户可以创建许多仓库。 docker CLI默认使用Docker的公共注册表。

注意：我们在这里使用Docker的公共注册表仅仅是因为它是免费和预先配置的，但有许多公共选择，甚至可以使用Docker Trusted Registry设置您自己的私有注册表。

##### 使用您的Docker ID登录

如果您没有Docker帐户，请在`cloud.docker.com`注册一个帐户。 记下你的用户名。

登录到本地计算机上的Docker公共注册表。

    $ docker login
##### 标记镜像

将本地镜像与注册表中的存储库相关联的符号是`username/repository：tag`。 这个标签是可选的，但推荐使用，因为它是注册管理机构为Docker镜像提供版本的机制。 为该上下文提供仓库并标记有意义的名称，例如`get-started：part2`。 这将镜像放入`get-started`仓库并将其标记为`part2`。

现在，把它放在一起来标记镜像。 使用您的用户名，仓库库和标签名`docker tag image`，以便将图像上传到您想要的目的地。 该命令的语法是：

    docker tag image username/repository:tag
列如：
    
    docker tag friendlyhello john/get-started:part2

运行`docker image ls`来查看新标记的镜像。

    $ docker image ls
    REPOSITORY               TAG                 IMAGE ID            CREATED             SIZE
    friendlyhello            latest              d9e555c53008        3 minutes ago       195MB
    john/get-started         part2               d9e555c53008        3 minutes ago       195MB
    python                   2.7-slim            1c7128a655f6        5 days ago          183MB
    ...

##### 发布镜像

将您的标记镜像上传到仓库：

    docker push username/repository:tag
    
一旦上传完成后，此上传的结果将公开发布。 如果您登录到Docker Hub，则可以通过其pull命令来拉取新镜像。

##### 从远程仓库中拉取并运行映像

从现在起，您可以使用`docker run`命令在任何机器上运行您的应用程序：

    docker run -p 4000:80 username/repository:tag

如果在本地机器上的镜像不可用，则将其从Docker仓库库中拉取。

    $ docker run -p 4000:80 john/get-started:part2
    Unable to find image 'john/get-started:part2' locally
    part2: Pulling from john/get-started
    10a267c67f42: Already exists
    f68a39a6a5e4: Already exists
    9beaffc0cf19: Already exists
    3c1fe835fb6b: Already exists
    4c9f1fa8fcb8: Already exists
    ee7d8f576a14: Already exists
    fbccdcced46e: Already exists
    Digest: sha256:0601c866aab2adcc6498200efd0f754037e909e5fd42069adeff72d1e2439068
    Status: Downloaded newer image for john/get-started:part2
     * Running on http://0.0.0.0:80/ (Press CTRL+C to quit)
     
无论`docker run`在哪里执行，它都会将您的镜像以及Python和requirements.txt中的所有依赖关系一起拉取下来，并运行您的代码。 它们都在一个整洁干净的小包中一起运行，并且不需要在您主机上安装任何Docker来运行它。


### 第三节.服务

#### 1.先决条件

1).安装docker的版本为1.13或者更高。
2).获取Docker Compose。 在Mac平台下的Docker和Windows平台下Docke中，它已预先安装，可以直接使用。关于Docker Compose怎么使用，后面将会详细介绍；在Linux系统上，您需要直接安装它。 如果不是win10系统或者其他Win系统在没有Hyper-V，需要使用Docker Toolbox来装载Docker。
3).你需要读懂本章的第一、第二节。
4).确保您已发布通过推送到注册表创建的`friendlyhello`镜像。 我们在这里使用该共享镜像。
5).确保你的镜像作为一个部署的容器. 运行这个命令, 在您的信息中输入用户名, 仓库和标志: `docker run -p 80:80 username/repo:tag`,然后访问`http://localhost/`。

#### 2.序言

在第三节中，我们扩展了我们的应用并实现了负载平衡。 要做到这一点，我们必须在分布式应用程序的层次结构中升级一级：服务。

堆
服务（本节介绍）
容器（第二节已经介绍）

#### 3.关于服务

在分布式应用程序中，应用程序的不同部分被称为“服务”。例如，如果您想象一个视频共享站点，它可能包含一个用于将应用程序数据存储在数据库中的服务，后面的视频转码服务用户上传的东西，前端的服务等等。

服务实际上只是“生产中的容器”。服务只运行一个镜像，但它编码图像运行的方式-应该使用哪个端口，容器应运行多少个副本，以便服务具有所需的容量，以及 等等。 缩放服务会更改运行该软件的容器实例的数量，从而为流程中的服务分配更多计算资源。

幸运的是，使用Docker平台定义，运行和扩展服务非常简单-只需编写一个docker-compose.yml文件即可。

#### 4.编写你的第一个`docker-compose.yml`文件

docker-compose.yml文件是一个YAML文件，它定义了Docker容器在生产中的行为方式。

##### docker-compose.yml

将此文件保存为docker-compose.yml，无论你在什么系统平台下。 确保您已将第二节中创建的镜像推送到注册表中，并通过用您的镜像替换`username/repo:tag`来更新此`.yml`文件。

    version: "3"
    services:
      web:
        # replace username/repo:tag with your name and image details
        image: username/repo:tag
        deploy:
          replicas: 5
          resources:
            limits:
              cpus: "0.1"
              memory: 50M
          restart_policy:
            condition: on-failure
        ports:
          - "80:80"
        networks:
          - webnet
    networks:
      webnet:

这个docker-compose.yml文件告诉Docker执行以下操作：

1).从注册表中拉取我们在第二节中上传的镜像。
2).运行该镜像的5个实例作为名为web的服务，限制每个实例使用最多10％的CPU（跨所有核心）和50MB的RAM。
3).如果一个失败，立即重启容器。
4).将主机上的端口80映射到Web的端口80。
5).指示web容器通过称为webnet的负载平衡网络共享端口80。 （在内部，容器本身在临时端口上发布到web的端口80）。
6).使用默认设置（这是一个负载平衡覆盖网络）定义webnet网络。

#### 5.运行新的负载均衡应用程序

在此之前，我们可以使用`docker stack deploy`命令来完成首次执行

    docker swarm init

注意：
关于上面这个命令，在第四节中我们将会介绍它的具体含义。如果你不执行Docker集群初始化命令，你会获得一个错误“这个节点不是集群管理节点”

现在，让我们来运行它，你需要给应用程序一个名字，在这里，我们就把他命名为`getstartedlab`

    docker stack deploy -c docker-compose.yml getstartedlab

单个服务栈在一台主机上运行我们部署的镜像容器实例

使用下面的命令为我们的每个应用程序查看服务ID号

    docker service ls
    
查看web服务的对外输出，首先关注应用程序的名字，如果名字和案列中的显示一样，名字是`getstartedlab_web`,服务的ID、包含副本的数量、镜像名字、端口也会相应的列出来，

单个容器运行在服务中被称为任务，每个任务都有唯一的ID，这个ID是数字化增长的，增长到`docker-compose.yml`文件中定义的副本数量，使用下面命令可以你的服务中的任务：

    docker service ps getstartedlab_web

如果你列出的是在你系统中的所有容器，任务将会上升显示，你可以通过下面命令过滤服务

    docker container ls -q

你可以在一个行中执行几次`curl -4 http://localhost`，然后去浏览器中输入URL点击刷新几次，效果如下

图片21:
    ![图片21](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/21.png  "图片21")

无论哪种方式，容器ID都会发生变化，从而显示负载平衡; 在每个请求中，以循环方式选择5个任务中的一个来响应。 容器ID与前一个命令（docker container ls -q）的输出相匹配。

#### 4.扩展应用程序

可以通过在docker-compose.yml中改变副本的值来扩展应用程序，保存改变，重新运行Docker栈部署命令：

    docker stack deploy -c docker-compose.yml getstartedlab

Docker执行一下就会就地地更新，不需要先杀死栈或杀死任何容器。

现在，重新运行`docker container ls -q`查看部署重配置情况。如果你扩展了副本，则会启动更多任务，因此还会启动更多容器。

##### 删除应用程序和集群

使用这个`docker stack rm`命令来删除应用程序:

    docker stack rm getstartedlab
删除集群

    docker swarm leave --force
 
用Docker建设并扩展您的应用程序非常简单。 您已经朝着学习如何在生产中运行容器迈出了一大步。 接下来，您将学习如何将这个应用程序作为Docker机器群集上的真正群体运行。

注意：像这样编写文件用于使用Docker定义应用程序，并且可以使用Docker Cloud将其上传到云提供商，或者使用Docker Enterprise Edition选择的任何硬件或云提供商。


### 第四节.集群

#### 1.先决条件

1).安装Docker版本1.13或更高版本。
2).按照第三节的先决条件中所述获取Docker Compose。
3).获取预装Mac平台Docker和Windows平台上的Dockers的Docker Machine，但在Linux系统上需要直接安装它。如果不是win10系统或者其他Win系统在没有Hyper-V，需要使用Docker Toolbox来装载Docker
4).看本章中的第一节和第二节
5)确保您已发布通过推送到注册表创建的`friendlyhello`镜像。 我们在这里使用该共享镜像。
6).确保你的镜像作为一个部署的容器. 运行这个命令, 在您的信息中输入用户名, 仓库和标志: `docker run -p 80:80 username/repo:tag`,然后访问`http://localhost/`。
7).方便地从第三节复制docker-compose.yml。

#### 2.序言

在第三节中，介绍了在第二节中编写的应用程序，并定义了它应该如何在生产环境中运行，将其转化为服务，并在此过程中将其扩展5个容器服务。

在第四节中，我们会将此应用程序部署到群集上，并在多台机器上运行它。 通过将多台机器连接到称为群集的“Dockerized”群集，使多容器，多机器应用成为可能。

#### 3.理解集群

Swarm是一组运行Docker并加入到集群中的机器。 发生这种情况后，您将继续运行您习惯的Docker命令，但现在它们将由群集管理器在群集上执行。 群体中的机器可以是物理的或虚拟的。加入群体后，这些物理机或者虚拟机被称为节点。

Swarm管理人员可以使用多种策略来运行容器，例如“最空节点”-它可以使用容器填充使用率最低的机器。 或者“全局”，它确保每台机器只获取指定容器的一个实例。指示swarm管理人员在Compose文件中使用这些策略，就像已经使用的策略一样。

集群管理者是集群中唯一可以执行命令的机器，或者授权其他机器作为工作者加入群体。 工人只是在那里提供能力，并没有权力告诉任何其他机器可以做什么和不可以做什么。

到目前为止，您已经在本地机器上以单主机模式使用Docker。 但是Docker也可以切换到集群模式，这就是使用集群的原因。 立即启用集群模式使当前的机器成为群管理器。 从此，Docker将运行在您管理的集群上执行命令，而不仅仅是在当前机器上执行。

#### 4.配置集群

一个集群由多个节点组成，可以是物理机器或虚拟机器。 基本概念很简单：运行`docker swarm init`来启用swarm模式，并让你的当前机器成为`swarm manager`，然后在其他机器上运行`docker swarm join`，让它们作为工作者加入`swarm`。 选择下面的选项卡，看看它是如何在各种情况下发挥作用的。 我们使用虚拟机快速创建一个双机群集，并将其转变为群集。

##### 创建一个集群

###### VMS在您的本地机器上(MAC, LINUX, WIN7和WIN8)

需要一个可以创建虚拟机（VM）的虚拟机管理程序，因此请为您的计算机的操作系统安装甲骨文的VirtualBox。关于VirtualBox的安装请查询相关资料，这里不做介绍

注意：如果在安装了Hyper-V的Windows系统（如Windows 10）上，则无需安装VirtualBox，而应该使用Hyper-V。 通过单击上面的Hyper-V选项卡查看Hyper-V系统的说明。 如果你使用的是Docker Toolbox，你应该已经安装了VirtualBox作为它的一部分。

现在，使用docker-machine创建一对VMS，使用VirtualBox驱动

    docker-machine create --driver virtualbox myvm1
    docker-machine create --driver virtualbox myvm2
    
    
###### VMS在本地机器(WIN10)

首先，快速为您的虚拟机（VM）创建一个虚拟交换机以便共享，以便它们可以相互连接。

1).启动Hyper-V管理器
2).点击右侧菜单中的虚拟交换管理器
3).单击创建类型为External的虚拟交换机
4).将它命名为myswitch，然后选中复选框以共享主机的活动网络适配器
5).现在，使用我们的节点管理工具docker-machine创建几个虚拟机：

    docker-machine create -d hyperv --hyperv-virtual-switch "myswitch" myvm1
    docker-machine create -d hyperv --hyperv-virtual-switch "myswitch" myvm2


###### 列出VMS和获取他们的IP地址

现在创建了两个VMS，名字叫做myvm1和myvm2

使用下面这个命令列出机器和取得他们的IP地址

    docker-machine ls

下面是命令行输出的结果：

    $ docker-machine ls
    NAME    ACTIVE   DRIVER       STATE     URL                         SWARM   DOCKER        ERRORS
    myvm1   -        virtualbox   Running   tcp://192.168.99.100:2376           v17.06.2-ce   
    myvm2   -        virtualbox   Running   tcp://192.168.99.101:2376           v17.06.2-ce   

###### 初始化集群和添加节点

第一台机器作为管理员，执行管理命令并认证其他节点加入集群，第二台机器是节点。

您可以使用docker-machine ssh将命令发送到您的VM。 指示myvm1成为一个拥有`docker swarm init`的`warm manager`并查看是否有这样的输出：

    $ docker-machine ssh myvm1 "docker swarm init --advertise-addr <myvm1 ip>"
    Swarm initialized: current node <node ID> is now a manager.

    To add a worker to this swarm, run the following command:

      docker swarm join \
      --token <token> \
      <myvm ip>:<port>

    To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.

 * 端口2377和2376

 总是在端口2377(集群管理端口)上运行 `docker swarm init` 和 `docker swarm join` 命令, 或根本不运行端口，并让其采用默认值.
 通过命令`docker-machine ls`获取到包括端口2376机器的IP地址，2376是Docker的守护端口。不要使用这个端口，否则你会遇到一些经验性错误

 * 使用SSH有问题吗？尝试使用 -native-ssh标志

 如果由于某些原因，您无法向集群管理机器发送命令，Docker Machine可以让您使用自己系统的SSH。 只需在调用ssh命令时指定--native-ssh标志：

    docker-machine --native-ssh ssh myvm1 ...

如您所见，对`docker swarm init`的响应包含一个预配置的`docker swarm join`命令，您可以在要添加的任何节点上运行该命令。 复制这个命令，并通过`docker-machine ssh`将它发送到myvm2，让myvm2作为一个工作节点的形式加入你的集群：

    $ docker-machine ssh myvm2 "docker swarm join \
    --token <token> \
    <ip>:2377"

恭喜，你已经创建了你的第一个群！

在管理器上运行docker节点ls以查看此群中的节点：

    $ docker-machine ssh myvm1 "docker node ls"
    ID                            HOSTNAME            STATUS              AVAILABILITY        MANAGER STATUS
    brtu9urxwfd5j0zrmkubhpkbd     myvm2               Ready               Active
    rihwohkh3ph38fhillhhb84sk *   myvm1               Ready               Active              Leader

 * 离开集群
 
 如果你想结束集群，你可以使用`docker swarm leave`来分离他们

#### 5.在集群上部署你的应用

困难的部分已经结束，现在仅仅需要重复在第三节中过程部署一个新的集群，只要记住有一个类似myvm1这样的集群管理者执行Docker命令；工作节点仅仅是为了容纳

##### 配置一个docker-machine shell脚本来管理swarm

到目前为止，您已经在Docker-machine ssh中将Docker命令包装了与虚拟机交互。 另一种选择是运行`docker-machine env <machine>`来获取并运行一个命令，该命令将当前shell配置为与VM上的Docker守护进程进行通信。 此方法对下一步更好，因为它允许您使用本地`docker-compose.yml`文件“远程”部署应用程序，而无需将其复制到任何位置。

键入`docker-machine env myvm1`，然后复制粘贴并运行作为输出最后一行提供的命令，以将shell配置swarm管理机器与myvm1交互。

配置shell的命令根据你是Mac，Linux还是Windows而有所不同，因此下面的分情况来介绍。

* Mac和Linux平台

###### MAC或LINUX上的DOCKER MACHINE SHELL环境

运行`docker-machine env myvm1`以获取命令来配置shell以与myvm1进行通信。

    $ docker-machine env myvm1
    export DOCKER_TLS_VERIFY="1"
    export DOCKER_HOST="tcp://192.168.99.100:2376"
    export DOCKER_CERT_PATH="/Users/sam/.docker/machine/machines/myvm1"
    export DOCKER_MACHINE_NAME="myvm1"
    # Run this command to configure your shell:
    # eval $(docker-machine env myvm1)

运行给定的命令来配置你的shell与myvm1进行通信。

    eval $(docker-machine env myvm1)

运行`docker-machine ls`以验证myvm1现在是活动机器，如旁边的星号所示。

    $ docker-machine ls
    NAME    ACTIVE   DRIVER       STATE     URL                         SWARM   DOCKER        ERRORS
    myvm1   *        virtualbox   Running   tcp://192.168.99.100:2376           v17.06.2-ce   
    myvm2   -        virtualbox   Running   tcp://192.168.99.101:2376           v17.06.2-ce   

* Windows平台

###### WINDOWS上的DOCKER MACHINE SHELL环境

运行`docker-machine env myvm1`以获取命令来配置shell以与myvm1进行通信。

    PS C:\Users\sam\sandbox\get-started> docker-machine env myvm1
    $Env:DOCKER_TLS_VERIFY = "1"
    $Env:DOCKER_HOST = "tcp://192.168.203.207:2376"
    $Env:DOCKER_CERT_PATH = "C:\Users\sam\.docker\machine\machines\myvm1"
    $Env:DOCKER_MACHINE_NAME = "myvm1"
    $Env:COMPOSE_CONVERT_WINDOWS_PATHS = "true"
    # Run this command to configure your shell:
    # & "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env myvm1 | Invoke-Expression

运行给定的命令来配置你的shell与myvm1进行通信。

    & "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env myvm1 | Invoke-Expression

运行`docker-machine ls`以验证myvm1是否为活动机器，如旁边的星号所示。

    PS C:PATH> docker-machine ls
    NAME    ACTIVE   DRIVER   STATE     URL                          SWARM   DOCKER        ERRORS
    myvm1   *        hyperv   Running   tcp://192.168.203.207:2376           v17.06.2-ce
    myvm2   -        hyperv   Running   tcp://192.168.200.181:2376           v17.06.2-ce

##### 在集群管理器上部署应用程序

现在你已经拥有了myvm1，你可以使用它的权限作为集群管理者来部署你的app，方法是使用你在myvm1中使用的相同的`docker stack deploy`命令和`docker-compose.yml`的本地副本。 需要几秒钟才能完成，部署需要一段时间才能完成。 在集群管理器上使用`docker service ps <service_name>`命令验证所有服务是否已被重新部署。

你可以通过`docker-machine`shell脚本配置连接到`myvm1`,并且你可以通过本地主机进入文件，在此之前确信你已经在第三节中创建`docker-compose.yml`同级目录下。

就像之前一样，运行下面的命令将你的应用程序部署到myvm1上

    docker stack deploy -c docker-compose.yml getstartedlab
到目前为止，你的应用程序已经部署到集群上了

注意：如果你的镜像存储在私有仓库而不是存储在Docker Hub上,你需要使用`docker login <your-registry>`来登录到仓库，并且要在上面的命令后面添加`--with-registry-auth` 标志来部署应用程序

    docker login registry.example.com
    docker stack deploy --with-registry-auth -c docker-compose.yml getstartedlab

这使用加密的WAL日志将登录令牌从本地客户端传递到部署服务的群集节点。 有了这些信息，这些节点就能够登录到仓库并提取镜像了。


现在你可以使用第三节中相同的Docker命令。只有这次注意到服务（和相关容器）已经在`myvm1`和`myvm2`之间分配了。

    $ docker stack ps getstartedlab

    ID            NAME                  IMAGE                   NODE   DESIRED STATE
    jq2g3qp8nzwx  getstartedlab_web.1   john/get-started:part2  myvm1  Running
    88wgshobzoxl  getstartedlab_web.2   john/get-started:part2  myvm2  Running
    vbb1qbkb0o2z  getstartedlab_web.3   john/get-started:part2  myvm2  Running
    ghii74p9budx  getstartedlab_web.4   john/get-started:part2  myvm1  Running
    0prmarhavs87  getstartedlab_web.5   john/get-started:part2  myvm2  Running

* 使用`docker-machine`和`docker-machine ssh`连接到VMs

1).要将`shell`设置为与`myvm2`等其他机器通信，只需在相同或不同`shell`中重新运行`docker-machine env`，然后运行给定命令指向`myvm2`。这总是特定于当前的shell。如果您更改为未配置的shell或打开一个新的shell，则需要重新运行这些命令。使用`docker-machine ls`列出机器，查看它们处于什么状态，获取IP地址，并找出连接到哪一个（如果有的话）。要了解更多信息，请参阅`Docker Machine`入门主题。

2).或者，您可以以`docker-machine ssh <machine>“<command>”`的形式封装Docker命令，该命令可直接登录到VM，但不会立即访问本地主机上的文件。

3).在Mac和Linux上，您可以使用`docker-machine scp <file> <machine>：〜`在计算机之间复制文件，但Windows用户需要像Git Bash这样的Linux终端模拟器才能运行。

本教程演示了`docker-machine ssh`和`docker-machine env`，因为这些都可以通过`docker-machine CLI`在所有平台上使用。

##### 访问集群

你可以通过IP地址进入`myvm1`或者`myvm2`

网络的创建在负载均衡之间是共享的。运行`docker-machine ls`来获取VMs的IP地址，并且通过浏览器来访问他们，点击刷新（或者仅仅curl他们）

图片22:
    ![图片22](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/22.png  "图片22")

有五个可能的容器ID全部随机循环，展示负载平衡。

两个IP地址工作的原因是群中的节点参与入口路由网格。 这可以确保部署在群集中某个端口的服务始终将该端口保留给自己，而不管实际运行容器的节点是什么。

* 如果遇到连接问题，下面方法可能帮助到你

请记住，要使用群集中的入口网络，在启用群集模式之前，需要在群集节点之间打开以下端口：

1).用于容器网络发现的端口7946 TCP/UDP
2).用于入口网络的端口4789UDP

#### 6.迭代和扩展你的应用程序

1).从这里你可以完成你在第二节和第三节中学到的一切。
2).通过更改`docker-compose.yml`文件来扩展应用程序。
3).通过编辑代码更改应用程序行为，然后重新构建并推送新图像。（要做到这一点，请按照之前用于构建应用程序和发布图像的相同步骤）。
4).无论哪种情况，只需再次运行`docker stack deploy`来部署这些更改。
5).可以使用您在myvm2上使用的相同`docker swarm join`命令将任何物理或虚拟机器加入此群集，并将容量添加到群集中。之后只需运行`docker stack`部署，并且您的应用程序可以利用新资源。

#### 7.清除和重置

##### 栈和集群

使用`docker stack rm`命令来删除栈，例如：

    docker stack rm getstartedlab

保持集群或删除它？

在稍后的某个时间点，如果您想要使用管理员的权限使用命令`docker-machine ssh myvm2`“`docker swarm leave`”或在在工作节点上使用`docker-machine ssh myvm1``“docker swarm leave --force”`删除此集群。 

##### 取消设置docker-machine shell变量设置

您可以使用以下命令取消当前shell中的docker-machine环境变量：
    
    eval $(docker-machine env -u)

##### 重启Docker机器

如果关不主机，Docker机器会停止运行，需要运行`docker-machine ls`命令来检查机器的状态

    $ docker-machine ls
    NAME    ACTIVE   DRIVER       STATE     URL   SWARM   DOCKER    ERRORS
    myvm1   -        virtualbox   Stopped                 Unknown
    myvm2   -        virtualbox   Stopped                 Unknown

要重新启动已停止的计算机，运行：

    docker-machine start <machine-name>

例如：

    $ docker-machine start myvm1
    Starting "myvm1"...
    (myvm1) Check network to re-create if needed...
    (myvm1) Waiting for an IP...
    Machine "myvm1" was started.
    Waiting for SSH to be available...
    Detecting the provisioner...
    Started machines may have new IP addresses. You may need to re-run the `docker-machine env` command.

    $ docker-machine start myvm2
    Starting "myvm2"...
    (myvm2) Check network to re-create if needed...
    (myvm2) Waiting for an IP...
    Machine "myvm2" was started.
    Waiting for SSH to be available...
    Detecting the provisioner...
    Started machines may have new IP addresses. You may need to re-run the `docker-machine env` command.


### 第五节.堆栈

#### 1.必备条件

1).安装Docker版本1.13或更高版本。
2).对本章的1-4节中所述的内容已经掌握
3).确保您创建friendlyhello镜像并发布到仓库。我们在这里使用您发布的镜像。
4).确保你的镜像作为一个部署的容器. 运行这个命令, 在您的信息中输入用户名, 仓库和标志: `docker run -p 80:80 username/repo:tag`,然后访问`http://localhost/`。
5).方便地复制第三节中创建的docker-compose.yml。
6).确保您在第4节中设置的机器正在运行并处于就绪状态。运行`docker-machine ls`来验证这一点。如果机器已停止，请运行`docker-machine start myvm1`以启动管理器节点，然后启动`docker-machine start myvm2`以启动工作节点。
7).让你在第4节创建的集群运行并处于就绪状态。运行`docker-machine ssh myvm1“docker node ls”`来验证这一点。如果集群已启动，则两个节点都会报告就绪状态。如果没有，请按照设置集群中的说明重新初始化集群并加入工作节点。

#### 2.概述

在第四节中，介绍了如何设置一个集群，这是一群运行Docker的机器，并为其部署了一个应用程序，其中容器在多台机器上运行。

在第五节中，将介绍分布式应用程序层次结构的顶层：堆栈。 堆栈是一组相互关联的服务，它们可以共享依赖关系，并且可以进行协调和缩放。单个堆栈能够定义和协调整个应用程序的功能（尽管非常复杂的应用程序可能需要使用多个堆栈）。

一些好消息是，从第三节开始，创建Compose文件并使用`docker stack deploy`命令，从技术上讲，咱们一直在使用堆栈。 但是，这是在单个主机上运行的单个服务堆栈，通常不会发生在生产环境中。在这里，你可以把你学到的东西，使多个服务相互关联，并在多台机器上运行它们。

做得很好，这就是你的主场！

#### 3.添加一个新服务并且重新部署

将服务添加到我们的docker-compose.yml文件很容易。首先，我们添加一个免费的可视化工具，让我们看看我们的集群如何调度容器。

1).在编辑器中打开`docker-compose.yml`使用下面的内容代替`docker-compose.yml`文件中的内容。确保用`username/repo:tag`来替代你镜像详细描述

    version: "3"
    services:
      web:
        # replace username/repo:tag with your name and image details
        image: username/repo:tag
        deploy:
          replicas: 5
          restart_policy:
            condition: on-failure
          resources:
            limits:
              cpus: "0.1"
              memory: 50M
        ports:
          - "80:80"
        networks:
          - webnet
      visualizer:
        image: dockersamples/visualizer:stable
        ports:
          - "8080:8080"
        volumes:
          - "/var/run/docker.sock:/var/run/docker.sock"
        deploy:
          placement:
            constraints: [node.role == manager]
        networks:
          - webnet
    networks:
      webnet:

这里新增的唯一东西就是peer服务web化，名为可视化器。 这里注意两件新事物：一个数据卷键，让可视化工具访问Docker的主机套接字文件和一个放置键，确保这项服务只能在群集管理器上运行 - 从不是在工作节点上运行。 这是因为容器是由Docker创建的一个开源项目构建的，它在一个图表中显示了集群上运行的Docker服务。

我们稍后会详细讨论放置约束和数据卷。

2).确保shell配置能与myvm1进行通信（在这里有完整的例子）。

运行`docker-machine ls`列出机器并确保您已连接到`myvm1`。

如果需要，重新运行`docker-machine env myvm1`，然后运行给定的命令来配置shell。

在Mac和Linux上的命令

    eval $(docker-machine env myvm1)
在Windows上的命令
    
    & "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env myvm1 | Invoke-Expression
3).重新在管理节点上运行`docker stack deploy`，并更新需要更新的任何服务

    $ docker stack deploy -c docker-compose.yml getstartedlab
    Updating service getstartedlab_web (id: angi1bf5e4to03qu9f93trnxm)
    Creating service getstartedlab_visualizer (id: l9mnwkeq2jiononb5ihz9u7a4)
    
4).查看可视化器

在Compose文件中看到，可视化器在端口8080上运行。通过运行`docker-machine ls`来获取您的其中一个节点的IP地址。 转到8080端口的IP地址，您可以看到可视化器正在运行：

图片23:
    ![图片23](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/23.png  "图片23")

可视化器的单个副本按照您的预期在管理器上运行，并且网络的5个实例遍布整个集群。 您可以通过运行`docker stack ps <stack>`来确认此可视化：

    docker stack ps getstartedlab

可视化器是一包含在堆栈中不依赖其他的任何东西可以运行运用程序的独立的服务。现在你也可以创建一个有依赖的服务，如：提供一个可视化容器的Redis服务

#### 4.持久化数据

让我们通过工作流的形式将一条或者更多的应用程序的数据存储到Redis中。

1.保存一个最后能够添加Redis服务的新的`docker-compose.yml`文件。确保在镜像描述栏中使用你自己的`username/repo:tag`来替代。

    version: "3"
    services:
      web:
        image: username/repo:tag   #此处请使用你自己的用户名、仓库名和tag标志来替代
        deploy:
          replicas: 5
          restart_policy:
            condition: on-failure
          resources:
            limits:
              cpus: "0.1"
              memory: 50M
        ports:
          - "80:80"
        networks:
          - webnet
      visualizer:
        image: dockersamples/visualizer:stable
        ports:
          - "8080:8080"
        volumes:
          - "/var/run/docker.sock:/var/run/docker.sock"
        deploy:
          placement:
            constraints: [node.role == manager]
        networks:
          - webnet
      redis:
        image: redis
        ports:
          - "6379:6379"
        volumes:
          - "/home/docker/data:/data"
        deploy:
          placement:
            constraints: [node.role == manager]
        command: redis-server --appendonly yes
        networks:
          - webnet
    networks:
      webnet:

在Docker库中有一个Redis官方镜像并且该镜像已经被授权为简短的名字-redis,因此如果拉取官方镜像，这里不需要`username/repo`项。Redis的默认端口是6379，已经通过Redis预配置并且映射到主机。在这里的我的Compose文件，我们假设他在广域网中-世界上任何地方都可以访问。这样你就可以选择使用你的任意节点的IP进入Redis桌面管理，并且管理你的Redis实例

最重要的是，在Redis指定的持久化数据的这个栈之间的部署有两件重要的事

* Redis总是运行在管理节点上，因此总是使用相同的文件系统
* 在容器内部主机文件系统中，Redis进入任意Redis存储数据的目录，都要使用 /data的方式进入

这样，对于你的Redis数据创建了一个“可信任的资源”在你的主机物理文件系统中。不这样的话，在容器的内部Redis将会存储它的数据在/data目录下，这样如果容器重新部署数据将会被销毁。

信任资源的两个组件

* 往Redis服务上面放置是受限制的，确保你总是使用相同的主机
* 你创建的数据卷让我们通过使用`./data`方式进入(在主机上)或者`/data`（在Redis容器内部）.当容器运行的时候，文件被存储`./data`在指定主机持久化、连续化

准备好使用stack部署你的新的Redis

2.在管理节点上创建一个`./data`目录

    docker-machine ssh myvm1 "mkdir ./data"

3.确保你的shell配置能够与`myvm1`相互通信（这儿有完整的例子）

* 执行`docker-machine ls`命令列出Docker虚机，并且确保你已经来接到`myvm1`，这是通过星号来标识的
* 如果有必要，重新执行`docker-machine env myvm1`命令，然后运行配置shell的命令

在Mac和Linux平台，命令如下

    eval $(docker-machine env myvm1)

在Windows平台，命令如下

    & "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env myvm1 | Invoke-Expression

4.一次或者多次运行`docker stack deploy`命令

    $ docker stack deploy -c docker-compose.yml getstartedlab

5.运行`docker service ls`命令来验证三个服务是不是像你期望的那样运行着了

    $ docker service ls
    ID                  NAME                       MODE                REPLICAS            IMAGE                             PORTS
    x7uij6xb4foj        getstartedlab_redis        replicated          1/1                 redis:latest                      *:6379->6379/tcp
    n5rvhm52ykq7        getstartedlab_visualizer   replicated          1/1                 dockersamples/visualizer:stable   *:8080->8080/tcp
    mifd433bti1d        getstartedlab_web          replicated          5/5                 orangesnap/getstarted:latest    *:80->80/tcp

6.检测你的一个节点上的web页面，如`http://192.168.99.101`,然后查看一下你的可视化器的结果，现在是不是活着并且向Redis里面存储数据

图片24:
    ![图片24](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/24.png  "图片24")

当然，通过节点的IP地址检测两个节点中的任意一个8080端口的可视化器，并注意查看伴随着Redis服务运行的可视化器服务

图片25:
    ![图片25](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/25.png  "图片25")

### 第六节.部署你的应用程序

#### 1.必备条件

1).安装Docker
2).满足第三节中获取`Docker Compose`的描述，第四节中获取`Docker Machine`的描述
3).阅读过第一节定向部分、学习了第二节中怎么创建容器
4).确保你已经将`friendlyhello`镜像创建并发布，并且将其推送到仓库，在这儿我们能够使用共享镜像
5).确保你的镜像做为一个部署容器能够工作，运行这个命令`docker run -p 80:80 username/repo:tag`,把命令中的username和repo:tag替换成你自己的，然后访问`http://localhost/`
6).有一个在第五节中手动创建的`docker-compose.yml`的版本

#### 2.简介

你一直在为整个教程编辑相同的Compose文件。 那么，好消息，该撰写文件在生产环境中的效果与在您的计算机上开发环境效果是相同。 在这里，我们通过一些选项来运行Dockerized应用程序。

#### 3.选择一种方式

#### 1).DockerCE（云提供者）

如果你在生产环境中使用Docker社区版中是可行的，您可以使用Docker Cloud帮助您管理流行服务提供商（如Amazon Web Services，DigitalOcean和Microsoft Azure）上的应用程序。

设置与部署

* 将Docker Cloud与您的首选提供商连接，授予Docker Cloud权限，以便为您自动配置和“Dockerize”VM。
* 使用Docker云创建你的计算资源和创建你的集群
* 部署你的app

注意：在这儿我们不能够链接到Docker云文档；确保你完成的每一步你都能回退回去。

##### 连接到Docker云

你可以使用标准模式或者集群模式运行Docker

如果你使用标准模式运行Docker云，下面提供Docker云服务商说明文档链接

* 亚马逊web服务设置指南 `https://docs.docker.com/docker-cloud/cloud-swarm/link-aws-swarm/`
* DigitalOcean设置指南 `https://docs.docker.com/docker-cloud/infrastructure/link-do/`
* Microsoft Azure设置指南 `https://docs.docker.com/docker-cloud/infrastructure/link-azure/`
* Packet设置指南 `https://docs.docker.com/docker-cloud/infrastructure/link-packet/`
* SoftLayer设置指南 `https://docs.docker.com/docker-cloud/infrastructure/link-softlayer/`
* 使用Docker Cloud代理来携带自己的主机 `https://docs.docker.com/docker-cloud/infrastructure/byoh/`

如果您在Swarm模式下运行（建议用于Amazon Web Services或Microsoft Azure），请跳至下一部分有关如何创建集群的部分。

##### 创建集群

准备创建集群

如果你打算在亚马逊web服务器上创建集群，下面是在AWS上自动创建集群的链接

    https://docs.docker.com/docker-cloud/cloud-swarm/create-cloud-swarm-aws/

如果你使用微软的Azure，下面是在Azure上自动创建集群的链接

    https://docs.docker.com/docker-cloud/cloud-swarm/create-cloud-swarm-azure/

否则，在Docker Cloud用户界面中创建节点，并通过Docker Cloud运行通过SSH学习的第四节中的`docker swarm init`和`docker swarm join`命令。 最后，通过单击屏幕顶部的切换开启Swarm模式，并注册刚刚创建的swarm。

注意：如果您使用Docker云代理自带主机，则此提供程序不支持集群模式。 您可以使用Docker Cloud注册您自己的现有集群。

##### 部署你的App到云上

1.通过Docker Cloud连接到您的群集。 有几种不同的连接方式：

从集群模式的Docker Cloud Web界面中，选择页面顶部的Swarms，单击要连接的群集，然后将给定的命令复制粘贴到命令行终端中。

图片26:
    ![图片26](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/26.png  "图片26")

或者

对于Mac版本和Windows版本的Docker，你可以直接通过桌面应用菜单连接到你的集群

图片27:
    ![图片27](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/27.png  "图片27")

无论哪种方式，这将打开一个终端，其上下文是本地计算机，但其Docker命令会路由到云服务提供商上运行的群集。 您可以直接访问本地文件系统和远程群集，从而启用纯Docker命令。

2.运行`docker stack deploy -c docker-compose.yml getstartedlab`来部署应用程序到云主机集群

    docker stack deploy -c docker-compose.yml getstartedlab

     Creating network getstartedlab_webnet
     Creating service getstartedlab_web
     Creating service getstartedlab_visualizer
     Creating service getstartedlab_redis

现在你的运用程序正在运行在云服务上

##### 运行一些集群命令来验证部署

您可以使用集群命令行来浏览和管理swarm。 以下是一些现在应该看起来很熟悉的例子：

使用`docker node ls`来列出节点

      [getstartedlab] ~ $ docker node ls
      ID                            HOSTNAME                                      STATUS              AVAILABILITY        MANAGER STATUS
      9442yi1zie2l34lj01frj3lsn     ip-172-31-5-208.us-west-1.compute.internal    Ready               Active              
      jr02vg153pfx6jr0j66624e8a     ip-172-31-6-237.us-west-1.compute.internal    Ready               Active              
      thpgwmoz3qefdvfzp7d9wzfvi     ip-172-31-18-121.us-west-1.compute.internal   Ready               Active              
      n2bsny0r2b8fey6013kwnom3m *   ip-172-31-20-217.us-west-1.compute.internal   Ready               Active              Leader

使用`docker service ls`来列出服务

    [getstartedlab] ~/sandbox/getstart $ docker service ls
    ID                  NAME                       MODE                REPLICAS            IMAGE                             PORTS
    x3jyx6uukog9        dockercloud-server-proxy   global              1/1                 dockercloud/server-proxy          *:2376->2376/tcp
    ioipby1vcxzm        getstartedlab_redis        replicated          0/1                 redis:latest                      *:6379->6379/tcp
    u5cxv7ppv5o0        getstartedlab_visualizer   replicated          0/1                 dockersamples/visualizer:stable   *:8080->8080/tcp
    vy7n2piyqrtr        getstartedlab_web          replicated          5/5                 sam/getstarted:part6    *:80->80/tcp

使用`docker service ps <service>`来查看服务的任务

    [getstartedlab] ~/sandbox/getstart $ docker service ps vy7n2piyqrtr
    ID                  NAME                  IMAGE                            NODE                                          DESIRED STATE       CURRENT STATE            ERROR               PORTS
    qrcd4a9lvjel        getstartedlab_web.1   sam/getstarted:part6   ip-172-31-5-208.us-west-1.compute.internal    Running             Running 20 seconds ago                       
    sknya8t4m51u        getstartedlab_web.2   sam/getstarted:part6   ip-172-31-6-237.us-west-1.compute.internal    Running             Running 17 seconds ago                       
    ia730lfnrslg        getstartedlab_web.3   sam/getstarted:part6   ip-172-31-20-217.us-west-1.compute.internal   Running             Running 21 seconds ago                       
    1edaa97h9u4k        getstartedlab_web.4   sam/getstarted:part6   ip-172-31-18-121.us-west-1.compute.internal   Running             Running 21 seconds ago                       
    uh64ez6ahuew        getstartedlab_web.5   sam/getstarted:part6   ip-172-31-18-121.us-west-1.compute.internal   Running             Running 22 seconds ago        

##### 在云供应商机器上开放服务端口

此时，您的应用作为一个集群部署在您的云提供商服务器上，正如刚刚运行的docker命令所证明的那样。 但是，您仍然需要在云服务器上打开端口，以便：

* 允许在工作节点上的web服务和Redis服务互相进行通信
* 允许入站流量通过工作节点上的Web服务，以便可以从Web浏览器访问Hello World和Visualizer。
* 允许运行管理器的服务器上的入站SSH流量（这可能已在您的云提供商上设置）

这些是您需要为每项服务公开的端口：

|    服务     |     类别     |        协议        |          端口        |
|------------|:------------:|-------------------|----------------------|
|     web    |      HTTP    |         TCP       |          80          |
| visualizer |   	HTTP	|         TCP	    |         8080         |
|   redis	 |      TCP	    |         TCP	    |         6379         |

这样做的方法因您的云提供商而异。

##### 使用亚马逊来做一个案例

1.登录AWS控制台，转至EC2控制板，然后单击进入运行实例以查看节点。

2.在左侧菜单中，转到网络和安全>安全组。

请参阅getstartedlab-Manager- <xxx>，getstartedlab-Nodes- <xxx>和getstartedlab-SwarmWide- <xxx>的与swarm相关的安全组。

3.为群体选择“节点”安全组。 组名是这样的：getstartedlab-NodeVpcSG-9HV9SMHDZT8C。

4.为`Web`，`visualizer`和`Redis`服务添加入站规则，为每个服务设置类型，协议和端口（如上表所示），然后单击保存以应用规则。

图片27-1:
    ![图片27-1](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/27-1.png  "图片27-1")

提示：保存新规则时，会为IPv4和IPv6样式地址自动创建HTTP和TCP端口。

图片28:
    ![图片28](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/28.png  "图片28")

5.转到运行实例列表，获取其中一名工作人员的公共DNS名称，并将其粘贴到Web浏览器的地址栏中。

图片29:
    ![图片29](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/29.png  "图片29")

就像本教程的前几部分一样，Hello World应用程序显示在端口80上，而Visualizer显示在端口8080上。

图片30:
    ![图片30](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/30.png  "图片30")

图片31:
    ![图片31](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/31.png  "图片31")
    
    
##### 迭代与清除

从这里你可以完成你在教程前面部分学到的所有知识。

通过更改docker-compose.yml文件来扩展应用程序，并使用`docker stack deploy`命令即时重新部署应用程序。

通过编辑代码更改应用程序行为，然后重新构建并推送新图像。(要做到这一点，请按照之前用于构建应用程序和发布图像的相同步骤)。

您可以使用`docker stack rm`拆卸堆栈。 例如：

    docker stack rm getstartedlab

与您在本地Docker机器虚拟机上运行集群的场景不同，不管您是否关闭本地主机，您的集群和部署在其上的所有应用都将继续在云服务器上运行。

#### 2).DockerEE（云提供者）

Docker Enterprise Edition的客户运行一个稳定的，商业支持的Docker Engine版本，作为附加组件，他们获得了一流管理软件Docker Datacenter。 您可以使用通用控制面板通过UI管理应用程序的各个方面，使用Docker Trusted Registry运行私人图像注册表，与LDAP提供商集成，使用Docker Content Trust签署制作镜像以及许多其他功能。

坏消息是：拥有官方Docker Enterprise版本的唯一云提供商是Amazon Web Services和Microsoft Azure。

好消息是：有一个单击模板可以在这些提供程序的每一个上快速部署Docker Enterprise：

* 亚马逊平台的DockerEE说明
    
    https://store.docker.com/editions/enterprise/docker-ee-aws?tab=description
    
* Azure平台的DockerEE

    https://store.docker.com/editions/enterprise/docker-ee-azure?tab=description
    
一旦你完成设置并且Datacenter正在运行，你可以直接在UI中部署你的Compose文件。

图片32:
    ![图片32](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/32.png  "图片32")
    
之后，您可以看到它正在运行，并且可以更改您选择的应用程序的任何方面，甚至可以编辑Compose文件本身。

图片33:
    ![图片33](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/33.png  "图片33")
    

## 第四章：Docker层次结构

### 第一节.Docker引擎

Docker Engine是一个包含以下主要组件的客户端-服务器应用程序：

* 一种称为守护进程（dockerd命令）的长期运行程序。
* REST API指定程序可用于与守护进程进行通信并指示其执行操作的接口。
* 命令行界面（CLI）客户端（docker命令）。

图片34:
    ![图片34](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/34.png  "图片34")

CLI使用Docker REST API通过脚本或直接CLI命令来控制Docker守护进程或与其进行交互。许多其他Docker应用程序使用底层的API和CLI。

守护进程创建并管理Docker对象，如图像，容器，网络和数据卷。

注意：Docker使用开放源代码Apache 2.0许可证进行许可。


### 第二节.Docker的架构

Docker使用客户端-服务器体系结构。 Docker客户端与Docker守护进程通信，Docker守护进程负责构建，运行和分发Docker容器。 Docker客户端和守护进程可以在同一个系统上运行，也可以将Docker客户端连接到远程Docker守护进程。 Docker客户端和守护进程使用REST API通过UNIX套接字或网络接口进行通信。

图片35:
    ![图片35](https://github.com/guoshijiang/docker-virtual-technology/blob/master/images/35.png  "图片35")

#### 1.Docker守护进程

Docker守护进程（dockerd）侦听Docker API请求并管理Docker对象（如图像，容器，网络和数据卷）。 守护进程还可以与其他守护进程通信来管理Docker服务。

#### 2.Docker客户端

Docker客户端（docker）是许多Docker用户与Docker进行交互的主要方式。 当你使用诸如`docker run`之类的命令时，客户端将这些命令发送到dockerd，dockerd执行这些命令。 docker命令使用Docker API。 Docker客户端可以与多个守护进程进行通信。

#### 3.Docker注册表

Docker注册表存储Docker镜像。 Docker Hub和Docker Cloud是任何人都可以使用的公共注册表，并且Docker默认配置为在Docker Hub上查找图像。 你甚至可以运行你自己的私人注册表。 如果您使用Docker Datacenter（DDC），它包括Docker Trusted Registry（DTR）。

当您使用`docker pull`或`docker run`命令时，所需的镜像将从配置的注册表中提取。 当您使用`docker push`命令时，您的镜像将被推送到您配置的注册表中。

Docker商店允许您购买和销售Docker镜像或免费发布。 例如，您可以购买包含来自软件供应商的应用程序或服务的Docker镜像，并使用镜像将应用程序部署到您的测试，临时和生产环境中。 您可以通过拉取新版本的镜像并重新部署容器来升级应用程序。

#### 4.Docker对象
当您使用Docker时，您正在创建和使用图像，容器，网络，数据卷，插件和其他对象。 本节简要介绍其中一些对象。

##### 镜像

镜像是一个只读模板，带有创建Docker容器的说明。 通常，镜像基于另一个镜像，并具有一些额外的自定义功能。 例如，你构建可以基于ubuntu镜像的镜像，但也会安装Apache Web服务器和应用程序，以及使应用程序运行所需的配置细节。

您可能会创建自己的镜像，或者您可能只能使用其他人创建并在注册表中发布的镜像。 为了构建您自己的镜像，您可以使用简单的语法创建一个Dockerfile，以定义创建镜像并运行它所需的步骤。 Dockerfile中的每条指令都会在镜像中创建一个层。 当您更改Dockerfile并重建镜像时，只重建那些已更改的镜像。 与其他虚拟化技术相比，这是使镜像轻量，小巧，快速的一部分。

##### 容器

容器是一个可以运行的镜像实例。你可使用Docker Api或者CLI创建，启动，停止，或者删除容器。您可以将容器连接到一个或多个网络，将存储器连接到它，甚至可以根据其当前状态创建新映像。

默认情况下，容器与其他容器及其主机相对隔离。 您可以控制容器的网络，存储或其他底层子系统与其他容器或主机的隔离程度。

容器由其镜像定义，以及在创建或启动容器时提供给它的任何配置选项。 当一个容器被移除时，其未被存储在永久存储器中的状态改变消失。

##### `docker run`命令示例

以下命令运行一个ubuntu容器，以交互方式附加到本地命令行会话，并运行/bin/bash。

    $ docker run -i -t ubuntu /bin/bash
    
当您运行此命令时，会发生以下情况（假定您正在使用默认的注册表配置）：

1).如果你本地没有Ubuntu镜像，Docker会从你配置的注册表中取出它，就好像你已经手动运行`docker pull ubuntu`一样。
2).Docker会创建一个新的容器，就好像您手动运行了docker容器创建命令一样。
3).Docker将一个读写文件系统分配给容器，作为其最后一层。这允许正在运行的容器在其本地文件系统中创建或修改文件和目录。
4).由于您没有指定任何网络选项，因此Docker会创建一个网络接口来将容器连接到默认网络。这包括分配一个IP地址给容器。默认情况下，容器可以使用主机的网络连接连接到外部网络。
5).Docker启动容器并执行/bin/bash。因为容器是交互式运行并且连接到终端（由于-i和-t）标志，所以您可以使用键盘提供输入，并将输出记录到您的终端。
6).当您键入exit以终止/bin/bash命令时，容器停止但不会被删除。您可以重新启动或删除它

##### 服务

通过服务，您可以跨多个Docker守护进程扩展容器，这些守护进程可以作为一个群组与多个管理人员和工作人员一起工作。 swarm中的每个成员都是Docker守护进程，守护进程都使用Docker API进行通信。 服务允许您定义所需的状态，例如在任何给定时间必须可用的服务的副本数量。 默认情况下，该服务在所有工作节点之间进行负载平衡。 对于消费者来说，Docker服务似乎是一个单一的应用程序。 Docker引擎在Docker 1.12及更高版本中支持swarm模式。

#### 5.基础技术

Docker使用Go编写，利用Linux内核的几个特性来提供其功能。

##### 命名空间

Docker使用名为空间的技术来提供称为容器的独立工作空间。当你运行一个容器时，Docker会为该容器创建一组命名空间。

这些名称空间提供了一个隔离层。 容器的每个方面都在单独的名称空间中运行，并且其访问权限限于该名称空间。

Docker引擎在Linux上使用如下的命名空间：

* pid命名空间：进程隔离（PID：进程ID）。
* 网络名称空间：管理网络接口（NET：网络）。
* ipc命名空间：管理对IPC资源的访问（IPC：InterProcess Communication）。
* mnt命名空间：管理文件系统挂载点（MNT：挂载）。
* uts命名空间：隔离内核和版本标识符。（UTS：Unix分时系统）。

##### 控制组

Linux上的Docker Engine也依赖于另一种称为控制组（cgroups）的技术。 cgroup将应用程序限制为一组特定的资源。 控制组允许Docker引擎将可用硬件资源共享给容器，并可选地强制实施限制和约束。 例如，您可以限制可用于特定容器的内存。

##### 联合文件系统

联合文件系统或UnionFS是通过创建图层进行操作的文件系统，使它们非常轻巧和快速。 Docker引擎使用UnionFS为容器提供构建块。 Docker引擎可以使用多种UnionFS变体，包括AUFS，btrfs，vfs和DeviceMapper。

##### 容器格式

Docker引擎将名称空间，控制组和UnionFS组合成一个名为容器格式的包装器。 默认的容器格式是libcontainer。 将来，Docker可以通过与诸如BSD Jails或Solaris Zones等技术集成来支持其他容器格式。

## 第五章：在Docker上开发你的应用程序

### 第一节.应用程序开发概述

这一页罗列出了使用Docker开发应用程序的资源

#### 1.在Docker上开发一个新的应用程序

如果你仅仅基于Docker开发一个新的分支的应用程序，检查这些资源，理解一些最常见的模式，这样你能从Docker获得更多的利益。

* 学习通过Dockerfile文件来构建一个镜像
* 使用多级构建的方式来保证你的镜像不要太臃肿
* 使用数据卷或者挂载的方式开管理应用程序
* 把应用程序扩展为集群服务
* 使用compose文件来定义你的应用程序栈
* 普通应用程序开发最好的例子

#### 2.学习指定语言基于Docker来开发应用程序

* Java开发者学习使用Docker开发应用程序链接 `https://github.com/docker/labs/tree/master/developer-tools/java/`
* 基于node.js来开发Docker应用程序链接 `https://github.com/docker/labs/tree/master/developer-tools/nodejs/porting`
* 基于Ruby来开发应用程序的链接 `https://github.com/docker/labs/tree/master/developer-tools/ruby`
* .Net的链接 `https://docs.docker.com/engine/examples/dotnetcore/`
*  ASP.NET的链接 `https://docs.docker.com/compose/aspnet-mssql-compose/`

#### 3.使用SDK或者API来开发

当你通过使用Docker写Dockerfile文件或者compose文件开发应用程序感到特别顺手的时候，这样的话提升一个级别，你可以使用docker引擎SDK通过Go语言或者Python语言直接调用Python的Api进行开发。

### 第二节.Docker开发最佳实践

以下开发模式已被证明有助于人们使用Docker构建应用程序。 如果您发现了我们应该添加的内容，可以给Docker官方提供建议。

#### 1.怎么保持你的镜像不臃肿

在启动容器或服务时，小镜像可以更快速地拉下来，并加载到内存中。 有几条经验法则可以保持镜像不臃肿：

* 从适当的基础镜像开始。 例如，如果您需要JDK，请考虑将您的镜像放在官方的openjdk镜像上，而不是从通用的Ubuntu镜像开始，并将openjdk作为Dockerfile的一部分安装。

* 使用多阶段构建。 例如，您可以使用maven镜像构建Java应用程序，然后重置为tomcat镜像，并将Java构件复制到正确位置以部署应用程序，所有这些都位于相同的Dockerfile中。 这意味着您的最终镜像不包含构建所引入的所有库和依赖项，但仅包含运行它们所需的工件和环境。


* * 如果需要使用不包含多级构建的Docker版本，请尽量减少Dockerfile中单独运行命令的数量，以减少镜像中的层数。 您可以通过将多个命令整合到单个RUN行并使用shell的机制将它们组合在一起来完成此操作。 考虑以下两个片段。 第一个在镜像中创建两个层，而第二个创建一个层。

    RUN apt-get -y update
    RUN apt-get install -y python

    RUN apt-get -y update && apt-get install -y python

* 如果您有多个共同的镜像，请考虑使用共享组件创建您自己的基本镜像，并在其上创建独特的镜像。 Docker只需要加载一次通用层，然后缓存。 这意味着您的衍生镜像更有效地使用Docker主机上的内存并更快地加载。

* 要保持生产镜像精简但允许调试，请考虑使用生产镜像作为调试镜像的基本镜像。 可以在生产镜像上添加其他测试或调试工具。

* 在构建镜像时，应始终使用有用的标签对其进行标记，这些标签将编码版本信息，预期目标（例如产品或测试），稳定性或在不同环境中部署应用程序时有用的其他信息进行编码。 不要依赖自动创建的最新标签。


#### 2.在何处和如何持久化应用程序数据

* 避免使用存储驱动程序将应用程序数据存储在容器的可写层中。 与使用数据卷或绑定挂载相比，这增加了容器的大小，并且从I/O角度来看效率较低。

* 而是使用数据卷存储数据。

* 适合使用绑定挂载的一种情况是在开发过程中，您可能需要挂载源目录或刚刚构建到容器中的二进制文件。 对于生产，请改用数据卷，将其安装到与您在开发过程中安装绑定安装程序相同的位置。

* 对于生产而言，使用秘密来存储服务使用的敏感应用程序数据，并将配置用于非敏感数据（如配置文件）。 如果您当前使用独立容器，请考虑迁移以使用单副本服务，以便您可以利用这些仅限于服务的功能。

#### 3.在可能的情况下使用集群服务

* 在可能的情况下，使用集群服务进行扩展的能力来设计您的应用程序。

* 即使您只需运行应用程序的单个实例，集群服务也会比独立容器提供多项优势。服务的配置是声明式的，Docker一直在努力使期望的和实际的状态保持同步。

* 网络和数据卷可以与集群服务连接和断开连接，并且Docker可以以不中断的方式重新部署各个服务容器。需要手动停止，移除和重新创建独立容器以适应配置更改。

* 一些功能（如存储机密和配置的功能）仅适用于服务而不是独立容器。这些功能允许您保持镜像尽可能通用，并避免将敏感数据存储在Docker镜像或容器本身内。

* 让`docker stack deploy`处理任何镜像，而不是使用`docker pull`。通过这种方式，您的部署不会尝试从发生故障的节点拉出。而且，当新节点添加到集群中时，镜像会自动拉出。

在集群服务的节点之间共享数据存在限制。 如果您将Docker用于AWS或Docker for Azure，则可以使用Cloudstor插件在集群服务节点之间共享数据。 您还可以将应用程序数据写入支持同时更新的单独数据库中。

#### 4.使用CI/CD进行测试和部署

* 当您检查对源代码管理的更改或创建拉取请求时，请使用`Docker Cloud`或其他`CI/CD`管道自动构建并标记Docker镜像并对其进行测试。 `Docker Cloud`也可以将测试过的应用直接部署到生产环境中。

* 通过要求您的开发，测试和安全团队在将镜像部署到生产环境中之前对其进行签名，您可以更进一步了解Docker EE。 通过这种方式，您可以确保在将镜像部署到生产环境之前，它已经通过开发，质量和安全团队进行测试和签名。

#### 5.开发和生产环境的差异

|                开发环境               |                  生产环境           | 
|--------------------------------------|------------------------------------|
| 使用绑定挂载使您的容器可以访问您的源代码    |       使用数据卷存储容器数据          |
| 使用Docker for Mac或Docker for Windows|如果可能的话，使用Docker EE，通过用户映射将Docker进程与主进程隔离开来| 
|           不要担心时间漂移	          |始终在Docker主机上和每个容器进程中运行NTP客户端，并将它们全部同步到同一个NTP服务器。 如果使用swarm服务，还要确保每个Docker节点将其时钟与容器同步到同一时间源。      	    | 

### 第三节.开发镜像

#### 1.编写Dockerfiles的最佳实践

这个部分的内容包含了建立高效镜像推荐的最佳实践和方法。

Docker通过阅读Dockerfile中的指令自动构建镜像，Dockerfile是一个包含构建给定镜像所需要的所有指令文本文件。 Dockerfile遵守特定的格式和指令集，您可以在Dockerfile参考中找到它们。

Docker镜像由只读层组成，每个层代表一个Dockerfile指令。 这些层是堆叠的，每个层都是上一层层变化的三角形。 看下面这个Dockerfile：

    FROM ubuntu:15.04
    COPY . /app
    RUN make /app
    CMD python /app/app.py

每一条指令创建一个镜像层

* FROM:通过ubuntu15.04镜像创建一个镜像层 
* COPY:从您的Docker客户端的当前目录添加文件
* RUN:使用make工具构建你的应用程序
* CMD:指定在容器内运行的命令

当您运行镜像并生成容器时，您会在基础镜像层的顶部添加一个新的可写镜像层（“容器镜像层”）。 对正在运行的容器所做的所有更改（如写入新文件，修改现有文件和删除文件）都会写入此可写容器层。

#### 2.一般准则和建议

##### 2.1.创建临时容器

由Dockerfile定义的映像应该生成尽可能短暂的容器。 通过“短暂的”，我们的意思是容器可以被停止和销毁，然后重建并用绝对最小的设置和配置代替。

##### 2.2.理解构建的上下文

当您发出docker build命令时，当前的工作目录被称为构建上下文。 默认情况下，假设Dockerfile位于此处，但可以使用文件标志（-f）指定不同的位置。 无论Dockerfile实际存在于哪里，当前目录中文件和目录的所有递归内容都将作为构建上下文发送到Docker守护进程。

* 构建上下文的例子

为构建上下文创建一个目录并且cd进到这个目录，将“hello”写入名为hello的文本文件，并创建一个Dockerfile来运行cat，从构建上下文（.）中构建镜像：

    mkdir myproject && cd myproject
    echo "hello" > hello
    echo -e "FROM busybox\nCOPY /hello /\nRUN cat /hello" > Dockerfile
    docker build -t helloapp:v1 .

将Dockerfile和hello移入单独的目录并构建第二个版本的镜像（不依赖上一次构建的缓存）。 使用-f指向Dockerfile并指定构建上下文的目录：

    mkdir -p dockerfiles context
    mv Dockerfile dockerfiles && mv hello context
    docker build --no-cache -t helloapp:v2 -f dockerfiles/Dockerfile context



无意中包含不需要构建镜像的文件会导致更大的构建上下文和更大的镜像大小。 这会增加构建镜像的时间，增加拉和推镜像的时间，容器运行时大小。 要查看构建上下文有多大，请在构建Dockerfile时查找如下所示的消息：

    Sending build context to Docker daemon  187.8MB

#### 3.通过stdin管道Dockerfile

Docker 17.05添加了通过stdin管道Dockerfile使用本地或远程构建上下文构建镜像的功能。 在早期版本中，使用stdin的Dockerfile构建一个镜像不会发送构建上下文。

##### 3.1.Docker17.04或者更低的版本

    docker build -t foo -<<EOF
    FROM busybox
    RUN echo "hello world"
    EOF

##### 3.2.Docker17.05和更高版本(本地构建上下)

    docker build -t . -f-<<EOF
    FROM busybox
    RUN echo "hello world"
    COPY . /my-copied-files
    EOF

##### 3.3.Docker17.05和更高的版本(远程构建上下文)

    docker build -t foo https://github.com/thajeztah/pgadmin4-docker.git -f-<<EOF
    FROM busybox
    COPY LICENSE config_local.py /usr/local/lib/python2.7/site-packages/pgadmin4/
    EOF

#### 4.排除.dockerignore

要排除与构建无关的文件（不重构源代码库），请使用.dockerignore文件。 该文件支持与.gitignore文件类似的排除模式。 

#### 5.使用多阶段构建

多阶段构建（在Docker 17.05或更高版本中）允许您大幅缩减最终镜像的大小，而不需要努力减少中间层和文件的数量。

由于镜像是在构建过程的最后阶段构建的，因此可以通过利用构建缓存来最小化镜像层。

例如，如果您的版本包含多个镜像层，您可以从较不经常更改的版本（以确保版本缓存可重复使用）对较频繁更改的版本进行排序：

* 安装构建应用程序所需的工具
* 安装或更新库依赖项
* 生成你的应用程序

Go应用程序的Dockerfile可能如下所示：

    FROM golang:1.9.2-alpine3.6 AS build

    # Install tools required for project
    # Run `docker build --no-cache .` to update dependencies
    RUN apk add --no-cache git
    RUN go get github.com/golang/dep/cmd/dep

    # List project dependencies with Gopkg.toml and Gopkg.lock
    # These layers are only re-built when Gopkg files are updated
    COPY Gopkg.lock Gopkg.toml /go/src/project/
    WORKDIR /go/src/project/
    # Install library dependencies
    RUN dep ensure -vendor-only

    # Copy the entire project and build it
    # This layer is rebuilt when a file changes in the project directory
    COPY . /go/src/project/
    RUN go build -o /bin/project

    # This results in a single layer image
    FROM scratch
    COPY --from=build /bin/project /bin/project
    ENTRYPOINT ["/bin/project"]
    CMD ["--help"]


#### 6.不要安装不必要的软件包

为了减少复杂性，依赖性，文件大小和构建时间，避免安装额外的或不必要的软件包，仅仅是因为它们可能“很高兴”。例如，您不需要在数据库镜像中包含文本编辑器。

#### 7.分离应用程序

每个容器应该只有一个焦点应用，解耦程序到多个容器中将会使容器在水平方向更加易于扩展和更容易重用。例如：一个web应用堆可能由三个分离的容器组成，每个容器都有自己独立的镜像通过分离的方式来管理web应用，数据库和内存缓存器。


限制每个容器对应一个进程是一个不错的规则，但这并不是硬性的规则，容器不仅仅能够通过初始化进程运行，很多程序可能会根据他们自己的额外的进程去运行。例如：Celery可以通过多个工作进程产生，Apache则可以针对每个请求产生一个进程。

用做好的方式来保证容器尽可能的干净和模块化。如果容器之间相互依赖的话，你可以使用docker网络来保证这些容器之间是可以通信的即可

#### 8.镜像层最少化原则

在老版本的docker中，镜像层数量最小化是很重要的，因为这可以确保应用的性能。下面的特征是添加减少这些限制

* 在docker1.10版本或者docker更高版本中，仅仅只有RUN,COPY,ADD指令能够创建镜像层。其他的指令只能创建临时或者中间的镜像，并且构建的时候并不能增加镜像的尺寸大小。

* 在Docker17.05及更高版本中，您可以执行多阶段构建，并仅将所需的工件复制到最终镜像中。 这允许您在中间构建阶段中包含工具和调试信息，而不会增加最终镜像的大小。

#### 9.对多行参数进行排序

只要有可能，通过按字母数字方式对多行参数进行排序，可以缓解以后的更改。 这有助于避免重复包并使列表更容易更新。 这也使PR更容易阅读和审查。 在反斜杠（\）之前添加空格也有帮助。

以下是buildpack-deps映像中的示例：

    RUN apt-get update && apt-get install -y \
      bzr \
      cvs \
      git \
      mercurial \
      subversion

#### 10.利用构建缓存

当构建镜像时，Docker会按步骤去执行Dockerfile中的指令，按指定的顺序执行每个指令。 在检查每条指令时，Docker会在其缓存中查找可以重用的现有镜像，而不是创建新的（重复）镜像。

如果您根本不想使用缓存，可以在docker build命令中使用--no-cache = true选项。 但是，如果你让Docker使用它的缓存，重要的是要了解它何时可以找到匹配的镜像。 Docker遵循的基本规则概述如下：

* 从已经在缓存中的父镜像开始，将下一条指令与从该基本镜像导出的所有子镜像进行比较，以查看它们中的一个是否使用完全相同的指令构建。 如果不是，则缓存无效。

* 在大多数情况下，只需将Dockerfile中的指令与其中一个子镜像进行比较即可。 但是，某些说明需要更多的检查和解释。

* 对于ADD和COPY指令，将检查镜像中文件的内容，并为每个文件计算校验和。 在这些校验和中不考虑文件的最后修改时间和最后访问时间。 在高速缓存查找期间，将校验和与现有映像中的校验和进行比较。 如果文件中有任何更改（例如内容和元数据），则缓存无效。

* 除了ADD和COPY命令之外，高速缓存检查不会查看容器中的文件以确定高速缓存匹配。 例如，在处理RUN apt-get -y update命令时，不检查容器中更新的文件以确定是否存在缓存命中。 在这种情况下，只需使用命令字符串本身来查找匹配项。

缓存无效后，所有后续Dockerfile命令都会生成新镜像，并且不使用缓存。

#### 11.Dockerfile指令集

这些建议旨在帮助您创建高效且可维护的Dockerfile。

##### 11.1.FROM

尽可能使用当前的官方存储库作为镜像的基础。 我们推荐Alpine镜像，因为它受到严格控制并且尺寸较小（目前小于5 MB），同时仍然是完整的Linux发行版。

FROM的使用格式如下：

    FROM <image> [AS <name>]

或者

    FROM <image>[:<tag>] [AS <name>]

或者

    FROM <image>[@<digest>] [AS <name>]

FROM指令初始化新的构建阶段并为后续指令设置基本镜像。 因此，有效的Dockerfile必须以FROM指令开头。 镜像可以是任何有效镜像-通过从公共存储库中提取镜像来启动它尤其容易。

* ARG是Dockerfile中唯一可以在FROM之前的指令。
* FROM可以在单个Dockerfile中多次出现以创建多个镜像，或者使用一个构建阶段作为另一个构建阶段的依赖项。 只需在每个新的FROM指令之前记下提交输出的最后一个镜像ID。 每个FROM指令清除先前指令创建的任何状态。
* 可以选择通过将`AS name`添加到FROM指令，可以将名称赋予新的构建阶段。 该名称可以在后续的`FROM`和`COPY --from = <name | index>`指令中使用，以引用此阶段构建的镜像。
* 标记或摘要值是可选的。 如果省略其中任何一个，则构建器默认采用最新标记。 如果找不到标记值，构建器将返回错误。

###### 理解ARG和FROM如何互动

* FROM指令支持在第一个FROM之前发生的任何ARG指令声明的变量。

        ARG  CODE_VERSION=latest
        FROM base:${CODE_VERSION}
        CMD  /code/run-app

        FROM extras:${CODE_VERSION}
        CMD  /code/run-extras

* 在FROM之前声明的ARG在构建阶段之外，因此在FROM之后的任何指令中都不能使用它。 要使用在第一个FROM之前声明的ARG的默认值，请使用没有构建阶段内的值的ARG指令：

        ARG VERSION=latest
        FROM busybox:$VERSION
        ARG VERSION
        RUN echo $VERSION > image_version

##### 11.2.LABEL

您可以为镜像添加标签，以帮助按项目组织镜像，记录许可信息，帮助实现自动化或出于其他原因。 对于每个标签，添加以LABEL开头并带有一个或多个键值对的行。 以下示例显示了不同的可接受格式。 内容包括解释性意见。

注意：必须引用带空格的字符串或必须转义空格。 内引号字符（“）也必须转义。

    LABEL com.example.version="0.0.1-beta"
    LABEL vendor1="ACME Incorporated"
    LABEL vendor2=ZENITH\ Incorporated
    LABEL com.example.release-date="2015-02-12"
    LABEL com.example.version.is-production=""

图像可以有多个标签。 在Docker 1.10之前，建议将所有标签组合到单个LABEL指令中，以防止创建额外的层。 这不再是必需的，但仍然支持组合标签。

    LABEL com.example.version="0.0.1-beta" com.example.release-date="2015-02-12"

上面也可以写成下面这样

    LABEL vendor=ACME\ Incorporated \
          com.example.is-beta= \
          com.example.is-production="" \
          com.example.version="0.0.1-beta" \
          com.example.release-date="2015-02-12"

后续将会有一章的内容讲解Docker对象LABEL


##### 11.3.RUN

RUN指令有两种形式
* ` RUN <command>`（shell格式，命令以shell的形式运行，在Linux系统上默认是`/bin/sh -c`, windows上是`cmd /S /C`）
* `RUN ["executable", "param1", "param2"]`(exec 形式)

RUN指令将在当前镜像之上的新镜像层中执行任何命令并提交结果。 生成的已提交镜像将用于`Dockerfile`中的下一步。

分层`RUN`指令和生成提交符合Docker的核心概念，其中提交开销小，并且可以从镜像历史中的任何点创建容器，就像源代码控制一样。

exec执行形式可以避免`shell`字符串重写，并使用不包含指定`shell`可执行文件的基本镜像来运行`RUN`指令。

可以使用`SHELL`命令更改`shell`形式的默认`shell`指令。

在shell形式的指令中，您可以使用`\`（反斜杠）将单个`RUN`指令继续到下一行。 例如，考虑以下两行：

    RUN /bin/bash -c 'source $HOME/.bashrc; \
    echo $HOME'

上面的内容相当于下面的这一行

    RUN /bin/bash -c 'source $HOME/.bashrc; echo $HOME'

###### 注意：

* 要使用除`“/ bin / sh”`之外的其他shell，请使用传入所需shell的exec形式。 例如，`RUN [“/ bin / bash”，“ - c”，“echo hello”`

* exec形式被解析为JSON数组，这意味着您必须在单词而不是单引号（'）周围使用双引号（“）。

* 与shell形式不同，exec形式不会调用命令shell。 这意味着不会发生正常的shell处理。 例如，`RUN [“echo”，“$ HOME”]`不会对`$HOME`执行变量替换。 如果你想要shell处理，那么要么使用shell形式，要么直接执行shell，例如：`RUN [“sh”，“ - c”，“echo $ HOME”]`。 当使用exec形式并直接执行shell时，就像shell形式的情况一样，它是执行环境变量扩展的shell，而不是docker。

* 在JSON形式中，必须转义反斜杠。 这在反斜杠是路径分隔符的Windows上尤为重要。 由于不是有效的JSON，以下行将被视为shell形式，并以意外方式失败：`RUN [“c：\windows\system32\tasklist.exe”]`; 此示例的正确语法是：`RUN [“C：\\\\窗户SYSTEM32\\ tasklist.exe“]`

在使用反斜杠分隔的多行上拆分长或复杂的RUN语句，以使Dockerfile更具可读性，可理解性和可维护性。


###### Run指令

1.APT-GET

RUN指令的最常用的使用案列可能就是`apt-get`应用，因为它在安装包的时候经常使用，所以`RUN apt-get`命令有几个需要注意的问题。

避免`RUN apt-get`升级和`dist-upgrade`，因为父映像中的许多“基本”包无法在非特权容器内升级。 如果父镜像中包含的包已过期，请与其维护人员联系。 如果您知道需要更新的特定包foo，请使用`apt-get install -y foo`自动更新。

始终将RUN apt-get update与apt-get install结合在同一个RUN语句中。 例如：

     RUN apt-get update && apt-get install -y \
            package-bar \
            package-baz \
            package-foo

在RUN语句中单独使用`apt-get update`会导致缓存问题，以及后续的`apt-get install`执行失败。 例如，假设你有一个Dockerfile：

    FROM ubuntu:14.04
    RUN apt-get update
    RUN apt-get install -y curl


构建镜像后，所有镜像层都在Docker缓存中。 假想您稍后通过添加额外的包来修改`apt-get install`：

    FROM ubuntu:14.04
        RUN apt-get update
        RUN apt-get install -y curl nginx

Docker将初始和修改的指令视为相同，并重用前面步骤中的缓存。 因此，不会执行apt-get更新，因为构建使用缓存版本。 由于apt-get更新未运行，因此您的构建可能会获得curl和nginx包的过时版本。

使用RUN apt-get update && apt-get install -y可确保您的Dockerfile安装最新的软件包版本，无需进一步编码或手动干预。 这种技术称为“缓存清除”。 您还可以通过指定包版本来实现缓存清除。 这称为版本固定，例如：

    RUN apt-get update && apt-get install -y \
            package-bar \
            package-baz \
            package-foo=1.3.*

版本固定会强制构建以检索特定版本，而不管缓存中的内容是什么。 此技术还可以减少由于所需包中的意外更改而导致的故障。

下面是一个结构良好的RUN指令，它演示了所有apt-get建议。

    RUN apt-get update && apt-get install -y \
        aufs-tools \
        automake \
        build-essential \
        curl \
        dpkg-sig \
        libcap-dev \
        libsqlite3-dev \
        mercurial \
        reprepro \
        ruby1.9.1 \
        ruby1.9.1-dev \
        s3cmd=1.1.* \
     && rm -rf /var/lib/apt/lists/*

`s3cmd`参数指定版本`1.1.*`。 如果映像以前使用的是旧版本，则指定新版本会导致`apt-get update`缓存失效，并确保安装新版本。 列出每行的包也可以防止包重复中的错误。

此外，当您通过删除/var/lib/apt/lists清理apt缓存时，它会减小镜像大小，因为apt缓存不存储在该镜像层中。 由于RUN语句以apt-get update开头，因此在apt-get install之前始终刷新包缓存。

 - 官方Debian和Ubuntu映像自动运行apt-get clean，因此不需要显式调用

2.使用pipes

某些RUN命令取决于使用管道符（|）将一个命令的输出传递到另一个命令的能力，如下例所示：

    RUN wget -O - https://some.site | wc -l > /number
    
Docker使用/ bin/sh -c解释器执行这些命令，该解释器仅评估管道中最后一个操作的退出代码以确定成功。 在上面的示例中，只要wc -l命令成功，即使wget命令失败，此构建步骤也会成功并生成新映像。

如果您希望命令因管道中任何阶段的错误而失败，请预先设置-o pipefail &&以确保意外错误可防止构建无意中成功。 例如：

    RUN ["/bin/bash", "-c", "set -o pipefail && wget -O - https://some.site | wc -l > /number"]

###### CMD指令

CMD指令有三种格式

* CMD ["executable","param1","param2"] (exec形式, 优先考虑形式)
* CMD ["param1","param2"] (默认参数入口点形式)
* CMD command param1 param2 (shell命令形式)

Dockerfile中只能有一条CMD指令。 如果列出多个CMD，则只有最后一个CMD才会生效。

CMD的主要目的是为执行容器提供默认值。 这些默认值可以包含可执行文件，也可以省略可执行文件，在这种情况下，您还必须指定ENTRYPOINT指令。

注意：如果使用CMD为ENTRYPOINT指令提供默认参数，则应使用JSON数组格式指定CMD和ENTRYPOINT指令。

注意：exec表单被解析为JSON数组，这意味着必须使用双引号（“）来围绕单词而不是单引号（'）

注意：与shell表单不同，exec表单不会调用命令shell。 这意味着不会发生正常的shell处理。 例如，CMD [“echo”，“$ HOME”]不会对$ HOME进行变量替换。 如果你想要shell处理，那么要么使用shell表单，要么直接执行shell，例如：CMD [“sh”，“ - c”，“echo $ HOME”]。 当使用exec表单并直接执行shell时，就像shell表单的情况一样，它是执行环境变量扩展的shell，而不是docker。

在shell或exec格式中使用时，CMD指令设置运行映像时要执行的命令。

如果你使用CMD的shell形式，那么<command>将在/bin/sh -c中执行：

        FROM ubuntu
        CMD echo "This is a test." | wc -

如果要在没有shell的情况下运行<command>，则必须将该命令表示为JSON数组，并提供可执行文件的完整路径。 此数组形式是CMD的首选格式。 任何其他参数必须在数组中单独表示为字符串：

        FROM ubuntu
        CMD ["/usr/bin/wc","--help"]

如果您希望容器每次都运行相同的可执行文件，那么您应该考虑将ENTRYPOINT与CMD结合使用。

如果用户指定了docker run的参数，那么它们将覆盖CMD中指定的默认值。

注意：不要将RUN与CMD混淆。 RUN实际上运行一个命令并提交结果; CMD在构建时不执行任何操作，但指定了镜像的预期命令。

CMD指令应该用于运行镜像包含的软件以及任何参数。 CMD应该几乎总是以CMD [“executable”，“param1”，“param2”......]的形式使用。 因此，如果图像用于服务，例如Apache和Rails，则可以运行类似CMD [“apache2”，“ - DFOREGROUND”]的内容。 实际上，建议将这种形式的指令用于任何基于服务的图像。

在大多数其他情况下，应该给CMD一个交互式shell，比如bash，python和perl。 例如，CMD [“perl”，“ - de0”]，CMD [“python”]或CMD [“php”，“ - a”]。 使用这个表单意味着当你执行像docker run -it python这样的东西时，你将被放入一个可用的shell中，准备好了。 CMD应该很少以CMD [“param”，“param”]的方式与ENTRYPOINT一起使用，除非您和您的预期用户已经非常熟悉ENTRYPOINT的工作原理。

###### EXPOSE指令

    EXPOSE <port> [<port>/<protocol>...]

EXPOSE指令是Docker容器在运行时用来指定监听的端口。 指定监听端口可以是TCP，也可是UDP，如果未指定协议，则默认为TCP。

EXPOSE指令实际上不发布端口。 它作为构建镜像的人和运行容器的人之间的一种文档，用于发布要发布的端口。 要在运行容器时实际发布端口，请在docker run上使用-p标志发布和映射一个或多个端口，或使用-P标志发布所有公开的端口并将它们映射到高阶端口。

默认情况下，EXPOSE假定为TCP。 您还可以指定UDP：

    EXPOSE 80/udp

要在TCP和UDP上公开，请包含两行：

    EXPOSE 80/tcp
    EXPOSE 80/udp

在这种情况下，如果将-P与docker run一起使用，则端口将针对TCP公开一次，针对UDP公开一次。 请记住，-P在主机上使用短暂的高阶主机端口，因此TCP和UDP的端口不同。

无论EXPOSE设置如何，您都可以使用-p标志在运行时覆盖它们。 例如

    docker run -p 80:80/tcp -p 80:80/udp ...
    
docker network命令支持创建用于容器之间通信的网络，而无需公开或发布特定端口，因为连接到网络的容器可以通过任何端口相互通信。 

###### ENV指令

    ENV <key> <value>
    ENV <key>=<value> ...

ENV指令将环境变量<key>设置为值<value>。 此值将在构建阶段中所有后续指令的环境中，并且也可以在许多内联替换。

ENV指令有两种形式。 第一种形式ENV <key> <value>，将单个变量设置为一个值。 第一个空格后面的整个字符串将被视为<value> - 包括空格字符。 该值将针对其他环境变量进行解释，因此如果未对其进行转义，则将删除引号字符。
    
第二种形式ENV <key> = <value> ...允许一次设置多个变量。 请注意，第二种形式在语法中使用等号（=），而第一种形式则不然。 与命令行解析一样，引号和反斜杠可用于在值内包含空格。
    
例如：

    ENV myName="John Doe" myDog=Rex\ The\ Dog \
        myCat=fluffy
    
或者

    ENV myName John Doe
    ENV myDog Rex The Dog
    ENV myCat fluffy

将在最终镜像中产生相同的净结果。

当从生成的镜像中运行容器时，使用ENV设置的环境变量将保持不变。 您可以使用docker inspect查看值，并使用docker run --env <key> = <value>更改它们。

注意：环境持久性可能会导致意外的副作用。 例如，设置ENV DEBIAN_FRONTEND非交互式可能会使基于Debian的图像上的apt-get用户感到困惑。 要为单个命令设置值，请使用RUN <key> = <value> <command>。
    
为了使新软件更易于运行，您可以使用ENV更新容器安装的软件的PATH环境变量。 例如，ENV PATH/usr/local/nginx/bin：$PATH确保CMD [“nginx”]正常工作。

ENV指令对于提供特定于您希望容纳的服务的必需环境变量也很有用，例如Postgres的PGDATA。

最后，ENV还可用于设置常用的版本号，以便更容易维护版本颠簸，如下例所示：

    ENV PG_MAJOR 9.3
    ENV PG_VERSION 9.3.4
    RUN curl -SL http://example.com/postgres-$PG_VERSION.tar.xz | tar -xJC /usr/src/postgress && …
    ENV PATH /usr/local/postgres-$PG_MAJOR/bin:$PATH

与在程序中使用常量变量（与硬编码值相反）类似，此方法允许您更改单个ENV指令以自动神奇地破坏容器中的软件版本。

每条ENV线都会创建一个新的中间层，就像RUN命令一样。 这意味着即使您在将来的镜像中取消设置环境变量，它仍然会在此镜像层中保留，并且可以转储其值。 您可以通过创建如下所示的Dockerfile来测试它，然后构建它。

    FROM alpine
    ENV ADMIN_USER="mark"
    RUN echo $ADMIN_USER > ./mark
    RUN unset ADMIN_USER
    CMD sh

    docker run --rm -it test sh echo $ADMIN_USER
    mark

要防止这种情况，并且确实取消设置环境变量，请使用带有shell命令的RUN命令，在单个镜像层中设置，使用和取消设置变量all。 您可以将命令分开; 要么＆&。 如果您使用第二种方法，并且其中一个命令失败，则docker构建也会失败。 这通常是一个好主意。 使用\作为Linux Dockerfiles的行继续符可以提高可读性。 您还可以将所有命令放入shell脚本中，并使用RUN命令运行该shell脚本。

    FROM alpine
    RUN export ADMIN_USER="mark" \
        && echo $ADMIN_USER > ./mark \
        && unset ADMIN_USER
    CMD sh

    docker run --rm -it test sh echo $ADMIN_USER


###### ADD或者COPY指令













































