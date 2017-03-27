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
