# Linux


## 前言

- 小白不建议使用Linux部署！
- 如果你是小白且实在想使用Linux系统部署但搞不来的话,可以试试[TRSS脚本的安装教程](#%E5%AE%89%E8%A3%85trss%E8%84%9A%E6%9C%AC)

## Ubuntu 20.04教程

- 本教程博客地址:https://qianxinwanjiu.com/yunzai-bot-linux-ubuntu/

>本文的环境：
>纯净的Ubuntu（版本20.04）

### 1. 安装宝塔面板

- 为什么要安装宝塔面板？
- 因为便于管理文件（更改配置文件、上传面板图等）

>使用以下命令安装：

```sh
wget -O install.sh https://download.bt.cn/install/install-ubuntu_6.0.sh && sudo sh install.sh ed8484bec
```

>安装完成后，记得保存输出的面板地址和账号密码

<img src="picture/Ubuntu/Ubuntu-bt1.png" width="50%">

<img src="picture/Ubuntu/Ubuntu-bt2.png" width="50%">

### 2. 安装Nodejs与redis

- 打开面板地址，绑定手机号（如果你没有账号，请前往https://bt.cn/register.html注册）

- 登陆成功后，会显示一键安装页面，叉掉即可（不需要，因为不建站）

- 然后打开软件商店，搜索nodejs，找到nodejs版本管理器，

<img src="picture/Ubuntu/Ubuntu-bt3.png" width="50%">

- 点击安装

<img src="picture/Ubuntu/Ubuntu-bt4.png" width="50%">


- 点击安装即可

- 然后来到此界面，按下图所示操作

<img src="picture/Ubuntu/Ubuntu-bt5.png" width="50%">

- 建议使用v16.18.0

<img src="picture/Ubuntu/Ubuntu-bt6.png" width="50%">

- 安装好后，点击右侧的模块管理，来到下图所示界面，按图操作

<img src="picture/Ubuntu/Ubuntu-bt7.png" width="50%">

- 安装完成，回到软件商店，搜索redis，按下图操作

<img src="picture/Ubuntu/Ubuntu-bt8.png" width="50%">

### 3. 安装Yunzai
- 回到SSH终端，安装GIT，以便拉取仓库

- 执行以下命令：

```sh
sudo apt-get install git
```

<img src="picture/Ubuntu/Ubuntu-git.png" width="50%">

- 等待执行完成

- 然后拉取Yunzai，使用以下命令：

```sh
git clone --depth=1 -b main https://gitee.com/Le-niao/Yunzai-Bot.git
```

- 大致输出以下内容（没有ERR或error就不用管）

```log
Cloning into 'Yunzai-Bot'...
remote: Enumerating objects: 1073, done.
remote: Counting objects: 100% (1073/1073), done.
remote: Compressing objects: 100% (1053/1053), done.
remote: Total 1073 (delta 25), reused 911 (delta 2), pack-reused 0Receiving objects: 100% (1073/1073), 18.37 MiB | 9.07 MiB/s
Receiving objects: 100% (1073/1073), 27.20 MiB | 11.79 MiB/s, done.
Resolving deltas: 100% (25/25), done.
Updating files: 100% (992/992), done.
```

- 然后cd进Yunzai根目录

```sh
cd Yunzai-Bot
```

- pnpm安装过了，所以直接执行

```sh
pnpm install -P
```

输出大致如下

```log
 WARN  deprecated uuid@3.4.0: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
Packages: +362
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Packages are hard linked from the content-addressable store to the virtual store.
  Content-addressable store is at: /root/.local/share/pnpm/store/v3
  Virtual store is at:             node_modules/.pnpm
Progress: resolved 498, reused 497, downloaded 0, added 362, done

dependencies:
+ art-template 4.13.2
+ chalk 5.0.1
+ chokidar 3.5.3
+ https-proxy-agent 5.0.1
+ inquirer 8.2.4
+ lodash 4.17.21
+ log4js 6.5.2
+ md5 2.3.0
+ moment 2.29.3
+ node-fetch 3.2.6
+ node-schedule 2.1.0
+ node-xlsx 0.21.0
+ oicq 2.3.1
+ patch-package 6.5.0
+ pm2 5.2.0
+ puppeteer 13.7.0
+ redis 4.1.0
+ yaml 2.1.1

devDependencies: skipped

Done in 13.5s
```

<img src="picture/Ubuntu/Ubuntu-pnpm.png" width="50%">

- 记住！WARN不要惊慌，看到ERR或者error才是你需要解决的

- 然后node app启动机器人，按提示操作即可

## CentOS 7.9.2111教程:

- 本教程地址:https://qianxinwanjiu.com/yunzai-linux-centos/#comment-29
- 前提条件
- 首先，请确保你的环境完全干净，不支持已部署项目的机器（易翻车）

- 本文示例系统：CentOS 7.9.2111

- 开始安装

### 1. 安装Nodejs

- 先安装dnf

```sh
yum install -y dnf
```

<img src="picture/CentOS/CentOS-dnf.png" width="50%">

- 使用dnf安装fedora的epel-release插件

```sh
dnf install epel-release
```

- 将存储库加到系统中

```sh
curl -fsSL https://rpm.nodesource.com/setup_16.x | sudo sh -
```

- 安装nodejs，推荐大版本号16

```sh
dnf module install nodejs:16 -y
```

<img src="picture/CentOS/CentOS-nodejs.png" width="50%">

- 然后测试是否正确安装

```sh
node -v
```

- 输出以下即为成功安装

```log
[root@CentOS7.9.2111 ~]# node -v
v16.19.0
```

<img src="picture/CentOS/CentOS-node-v.png" width="50%">

### 2. 安装redis
- 使用以下命令安装并启动redis

```sh
yum -y install redis && redis-server --daemonize yes
```

- 如果像下图一样报错，那么是你没安装epel，返回上文查看命令

<img src="picture/CentOS/CentOS-error.png" width="50%">

### 3. 安装GIT

```sh
dnf install git -y
```

### 4. 克隆仓库
- 使用以下命令克隆仓库

- 国内服务器（Gitee源）

```sh
git clone --depth=1 -b main https://gitee.com/Le-niao/Yunzai-Bot.git
```

- 国外服务器（GitHub源）

```sh
git clone --depth=1 -b main https://github.com/Le-niao/Yunzai-Bot.git
```

<img src="picture/CentOS/CentOS-git.png" width="50%">

### 5. 安装依赖
- cd进Yunzai根目录（别告诉我你不会cd）

```sh
cd Yunzai-Bot
```

- 然后安装pnpm(-g表示全局)

```sh
npm install pnpm -g
```

<img src="picture/CentOS/CentOS-npm.png" width="50%">

- 用pnpm安装依赖

```sh
pnpm install -P
```

<img src="picture/CentOS/CentOS-pnpm.png" width="50%">

- 还需要安装Chrome依赖库

```sh
yum install pango.x86_64 libXcomposite.x86_64 libXcursor.x86_64 libXdamage.x86_64 libXext.x86_64 libXi.x86_64 libXtst.x86_64 cups-libs.x86_64 libXScrnSaver.x86_64 libXrandr.x86_64 GConf2.x86_64 alsa-lib.x86_64 atk.x86_64 gtk3.x86_64 -y && yum install libdrm libgbm libxshmfence -y && yum install nss -y && yum update nss -y
```

<img src="picture/CentOS/CentOS-Chrome.png" width="50%">

### 6. 安装中文字体，顺便把系统语言切换为中文

```sh
yum groupinstall fonts -y
```

<img src="picture/CentOS/CentOS-zh_CN1.png" width="50%">

- 然后查看当前系统所有语言包

```sh
locale -a
```

<img src="picture/CentOS/CentOS-zh_CN2.png" width="50%">

- 往下翻，找到zh_CN.utf-8

<img src="picture/CentOS/CentOS-zh_CN3.png" width="50%">

- 切换

```sh
localectl set-locale LANG=zh_CN.UTF-8
```

<img src="picture/CentOS/CentOS-zh_CN4.png" width="50%">

- 然后重启

### 7. 启动Yunzai并按提示操作即可

```sh
node app
```

<img src="picture/CentOS/CentOS-nodeapp.png" width="50%">

