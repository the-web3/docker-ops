
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
