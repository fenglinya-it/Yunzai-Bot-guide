# Yunzai-Bot指南

## 简介

[![](https://profile-counter.glitch.me/eihei/count.svg)](https://gitee.com/lin-zhi-xuan/eihei)
- Yunzai-Bot是原神qq群机器人，通过米游社接口，查询原神游戏信息，快速生成图片返回，
- 此指南是教你如何安装Yunzai-Bot和它的插件，编写插件和一些问题的解决方法。
- 本指南暂未完善，欢迎大家提交Issues和Pull Requests
- 求个star，谢谢
- 我的博客:[qianxinwanjiu](https://qianxinwanjiu.com/eihei/)
- 我的仓库:[gitee](https://gitee.com/lin-zhi-xuan/eihei)

## 目录

- [Yunzai-Bot的Windows安装教程](https://gitee.com/lin-zhi-xuan/eihei#windows)

  - [安装git](https://gitee.com/lin-zhi-xuan/eihei/tree/master#%E5%AE%89%E8%A3%85git)
  - [安装redis](https://gitee.com/lin-zhi-xuan/eihei/tree/master#%E5%AE%89%E8%A3%85redis)
  - [安装Yunzai-Bot本体](https://gitee.com/lin-zhi-xuan/eihei/tree/master#%E5%AE%89%E8%A3%85yunzai-bot%E6%9C%AC%E4%BD%93)

- [Yunzai-Bot的Linux安装教程](https://gitee.com/lin-zhi-xuan/eihei/tree/master/#linux)

  - [Ubuntu20.04教程](https://gitee.com/lin-zhi-xuan/eihei/blob/master/Linux.md#ubuntu-2004%E6%95%99%E7%A8%8B)
  - [CentOS 7.9.2111](https://gitee.com/lin-zhi-xuan/eihei/blob/master/Linux.md#centos-792111%E6%95%99%E7%A8%8B)

- [基础操作](https://gitee.com/lin-zhi-xuan/eihei#%E5%9F%BA%E7%A1%80%E6%93%8D%E4%BD%9C)

- [目录说明](https://gitee.com/lin-zhi-xuan/eihei#%E7%9B%AE%E5%BD%95%E8%AF%B4%E6%98%8E)

- [ffmpeg安装教程](https://gitee.com/lin-zhi-xuan/eihei#ffmpeg%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B)

- [插件安装教程](https://gitee.com/lin-zhi-xuan/eihei#%E6%8F%92%E4%BB%B6%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B)
 
  - [锅巴插件(Guoba-Plugin)](https://gitee.com/lin-zhi-xuan/eihei#%E9%94%85%E5%B7%B4%E6%8F%92%E4%BB%B6)
  - [喵喵插件 (miao-plugin)](https://gitee.com/lin-zhi-xuan/eihei#%E5%96%B5%E5%96%B5%E6%8F%92%E4%BB%B6-miao-plugin)
  - [抽卡插件 (flower-plugin)](https://gitee.com/lin-zhi-xuan/eihei#%E6%8A%BD%E5%8D%A1%E6%8F%92%E4%BB%B6-flower-plugin)
  - [py插件](https://gitee.com/lin-zhi-xuan/eihei#py%E6%8F%92%E4%BB%B6)
  - [单个js格式插件通用安装方法](https://gitee.com/lin-zhi-xuan/eihei#%E5%8D%95%E4%B8%AAjs%E6%A0%BC%E5%BC%8F%E6%8F%92%E4%BB%B6%E9%80%9A%E7%94%A8%E5%AE%89%E8%A3%85%E6%96%B9%E6%B3%95)

- [常用链接](https://gitee.com/lin-zhi-xuan/eihei#%E5%B8%B8%E7%94%A8%E9%93%BE%E6%8E%A5)

- [问题解答](https://gitee.com/lin-zhi-xuan/eihei#%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94)

- [Yunzai-Bot插件编写教学](https://gitee.com/lin-zhi-xuan/eihei#yunzai-bot%E6%8F%92%E4%BB%B6%E7%BC%96%E5%86%99%E6%95%99%E5%AD%A6)

## 安装Yunzai-Bot

### Windows:

- 学不会怎么办，V我50我手把手教你

- 环境准备:[Node.js](http://nodejs.cn/download/)(建议版本v16.18.0),[redis](https://wwrl.lanzouw.com/iB1f70hizgxa),[git](https://wwrl.lanzouw.com/iBjDY0hizgre)

####  安装git

- 下载地址[git](https://wwrl.lanzouw.com/iBjDY0hizgre),密码:114514

<img src="picture/Windows/Windows-git.png" width="50%">

- 一直点next

#### 安装redis

- 下载地址[redis](https://wwrl.lanzouw.com/iB1f70hizgxa),密码:114514

- 解压后启动redis-server.exe这个文件。

- 要一直开着，不能关掉。

<img src="picture/Windows/Windows-redis.png" width="50%">

#### 安装Yunzai-Bot本体

1. 新建一个文件夹(也可以不建)，命名随便，最好别用中文

2. 选个拉取方式:

**使用git-bash**

- 1.1 右键文件夹，选择git bash here

<img src="picture/Windows/Windows-gitbash.png" width="50%">

**使用原生自带终端**

- 2.1 进入你要安装Yunzai的文件夹

- 2.2 打开终端(在文件夹路径处将文件家路径改为cmd或者powershell)

3. 克隆项目

- 命令

```bash
git clone --depth=1 -b main https://gitee.com/Le-niao/Yunzai-Bot.git
```

<img src="picture/Windows/Windows-gitclone.png" width="50%">

4. 进入Yunzai目录

```bash
cd Yunzai-Bot 
```

<img src="picture/Windows/Windows-cd.png" width="50%">

5. 安装pnpm，已安装的可以跳过

```bash
npm install pnpm -g
```

- （因为我已经安装过了，所以就不放图了）

- 这里会发生的一些问题：
    输完卡住不动了怎么办？或者提示 `npm ERR！`？或者其他的报错？
    原因：你的服务器网络太差了，根本下载不动，没问题才怪了。
    解决方案：换源，执行命令来更换淘宝镜像源 `npm config set registry http://registry.npm.taobao.org` 然后再次执行安装 pnpm 的命令 `npm install pnpm -g`  
    就是可能有点后遗症，更换镜像源后有微小概率导致后续安装出现问题

6. 安装依赖

```bash
pnpm install -P
```

<img src="picture/Windows/Windows-pnpm.png" width="50%">

7. 运行（首次运行按提示输入登录）

```bash
node app
```

<img src="picture/Windows/Windows-nodeapp.png" width="50%">

- 如果觉得麻烦，可使用脚本：

>新建一个文件,把后缀改成bat,然后点击编辑

- 把下面代码复制进去，然后进行修改:

- 第一行中，第一个双引号无需填写，第二个双引号填写你redis路径
- 第二行填写你Yunzai-Bot根目录

```bat
start "" "C:/redis/redis-server.exe"
cd C:/Yunzai-Bot
node app
pause
```

- 改完后保存运行即可食用

### Linux

- 教程中的操作系统有(Ubuntu 20.04),(CentOS 7.9.2111)

- [Linux](./Linux.md)

## 基础操作

- 启动云崽： `node app`

- 查看日志： `pnpm run log`

- 后台运行： `pnpm start`

- 关闭云崽： 对着机器人发送 `#关机`，或者在关掉云崽运行窗口

- 功能列表： `#帮助`,`#插件名称+帮助`

- 更新云崽： `#全部更新`,`#强制更新`，`#更新`,`git pull`

- 重置云崽的部分设置(QQ 号，主人 QQ 等)： `pnpm run login`

---

## 目录说明

| 目录                     | 说明                           |
| ------------------------ | ------------------------------ |
| config\config\qq.yaml    | 可以修改登录方式，QQ 号        |
| config\config\redis.yaml | redis的设置（非必要别修改）        |
| config\config\other.yaml | 可以修改主人 QQ                |
| data\face                | 存放添加表情的位置             |
| data\MysCookie           | 存放 cookie 的位置             |
| logs\                    | 存放日志文件的位置              |
| plugins\example          | 存放 js 插件的位置             |
| Yunzai-Bot\plugins       | 存放大型插件的位置，如喵喵插件 |

## ffmpeg安装教程

1. 先下载压缩包
- ffmpeg下载链接[☞ffmpeg](https://wwrl.lanzouw.com/),密码114514

2. 下载完后解压,位置随便

3. 之后找到ffmpeg.exe和ffprobe.exe,复制文件路径

<img src="picture/ffmpeg/ffmpeg-1.png" width="50%">

4. 填写路径,有两种方法。

**直接修改配置文件**

- 之后找到配置文件,如下图

<img src="picture/ffmpeg/ffmpeg-2.png" width="50%">

- 最后把路径粘贴到下图的位置(注意:冒号后面有空格)

<img src="picture/ffmpeg/ffmpeg-3.png" width="50%">

**锅巴里面设置**

1. 先登陆锅巴

2. 然后点配置管理-->基础配置

3. 把路径粘贴进去

4. 最后点保存

<img src="picture/ffmpeg/ffmpeg-4.png" width="50%">

>注意事项:
>路径不能有空格，必须用单引号，必须用反斜杠。
>有些时候日志提示 `请检查ffmpeg配置` 可能是插件本身的问题，而不是你的 ffmpeg 没配置好

## 插件安装教程

- 注：均为V3插件

### [锅巴插件(Guoba-Plugin)](https://gitee.com/guoba-yunzai/guoba-plugin) 

- 主要提供云崽的网页端后台管理界面功能
- 安装教程：
- 第 1 步：下载插件

- 在云崽根目录下打开终端，运行

```bash
git clone --depth=1 https://gitee.com/guoba-yunzai/guoba-plugin.git ./plugins/Guoba-Plugin/
```

- 第 2 步：安装依赖

> 注：如果你不是通过`pnpm`安装的云崽，那么请【**不要**】使用此方式，请看`方式2`

如果你是使用`pnpm`安装的云崽，那么只需要在云崽根目录下运行此命令即可：

```bash
pnpm install --filter=guoba-plugin
```

> 注：请务必直接复制提供的命令，否则可能会导致依赖丢失的情况，若发生需自行重新安装。<br>
> `--filter=guoba-plugin`：只安装`guoba-plugin`下的依赖，其他依赖不处理，防止丢失。

- 第 3 步：运行插件

依赖安装完毕之后，直接运行即可，默认运行端口号是：50831

> 可在 config/application.yaml 中修改

启动完成之后，可以在控制台中看到网页地址，复制到浏览器中即可访问。

如果访问不到，请发送`#锅巴帮助`指令获取帮助。

### [喵喵插件 (miao-plugin)](https://gitee.com/yoimiya-kokomi/miao-plugin)

- Miao-Plugin是一个Yunzai-Bot的升级插件，提供包括角色查询等升级功能。

- 具体功能可在安装插件后 通过 #喵喵帮助 进行查看。如需进行设置可通过 #喵喵设置 命令进行管理。

- 推荐使用git进行安装，以方便后续升级。在Yunzai根目录夹打开终端，运行

-  使用gitee

```bash
git clone https://gitee.com/yoimiya-kokomi/miao-plugin.git ./plugins/miao-plugin/
```

- 进行安装。建议使用上述命令进行安装，以便于后续更新。 管理员发送`#喵喵更新`即可自动更新

### [抽卡插件 (flower-plugin)](https://gitee.com/Nwflower/flower-plugin)

- flower-plugin是一个适用于V3版本Yunzai-Bot的原神图鉴插件包，主要提供拓展抽卡功能，意在不修改本体抽卡卡池信息的情况下提供自定义卡池的拓展

- 在Yunzai-Bot根目录下，运行cmd，输入以下指令

```bash
git clone --depth=1 https://gitee.com/Nwflower/flower-plugin.git ./plugins/flower-plugin/
```

### py插件

- 我个人的建议是：
- 别去费精力装了
- 直接装个nonebot吧
- 换个登录端口实现1号俩机器人

### [单个js格式插件通用安装方法](https://gitee.com/yhArcadia/Yunzai-Bot-plugins-index?_from=gitee_search#js%E6%8F%92%E4%BB%B6%E7%B4%A2%E5%BC%95)

- 超级简单，只要把插件下载好后放入 `Yunzai-bot/plugins/example` 里即可 
<img src="picture/wenti/js-plugins.png" width="100%">

## 常用链接

>下载链接（均为网盘）有密码的均为114514

|名称|下载地址|
|---|---|
|redis|[☞redis](https://wwrl.lanzouw.com/iB1f70hizgxa)|
|git|[☞git](https://wwrl.lanzouw.com/iBjDY0hizgre)|
|node.js|[☞node.js](http://nodejs.cn/download/)|
|python3.8|[☞python3.8](https://wwrl.lanzouw.com/iK7uS0ixl0fi)|
|ffmpeg|[☞ffmpeg](https://wwrl.lanzouw.com/)|
|滑块验证助手|[☞滑块验证](https://maupdate.rainchan.win/txcaptcha.apk)|


- 官方文档地址:[☞Yunzai-Bot](https://docs.yunzai.org/)
- Yunzai-Bot插件库：[☞Github](https://gitee.com/yhArcadia/Yunzai-Bot-plugins-index)/[☞Gitee](https://gitee.com/yhArcadia/Yunzai-Bot-plugins-index)
- Yunzai-Bot（V3）：[☞Github](https://gitee.com/Le-niao/Yunzai-Bot)/[☞Gitee](https://gitee.com/Le-niao/Yunzai-Bot) 
- Yunzai-Bot（V2）：[☞Github](https://gitee.com/yoimiya-kokomi/Yunzai-Bot)/[☞Gitee](https://gitee.com/yoimiya-kokomi/Yunzai-Bot) 

## 问题解答

- [问题解答](./issue.md)

## Yunzai-Bot插件编写教学

- [Yunzai-Bot插件编写教学](./plugins.md)

## 交流群

|群名|群主|
|----|----|
|[原神交流](https://qm.qq.com/cgi-bin/qm/qr?k=Cu1TnfTNNOdhx0lv17qbnTzp9lhOy_dJ&jump_from=webapi&authKey=8cmxRdVRamzJn0xPI2yet1a//X16faoVcTqD6P2vn/PIgJECkquiq8dyEoSgUJKt)|[@eihei](https://gitee.com/lin-zhi-xuan)|


## Yunzai-Bot代搭

- 详情请见[Yunzai-Bot代搭](./daida.md)

## 赞助

- 编写不易

- [欸嘿爱发电](https://afdian.net/a/20091124eihei)
- [qianxinwanjiu爱发电](https://afdian.net/a/qianxinwanjiu)

## 开学通知

- 作者我已于2月6号开学，以后随缘更新，大概1周会有一次更新（没有跑路！没有跑路！没有跑路！）






