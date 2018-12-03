
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
    
