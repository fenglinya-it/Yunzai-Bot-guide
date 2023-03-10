# 问题解答

## 前言:遇到问题怎么办

- 先不要急着问
- 重启一下试试
- 重装一下试试
- 换台设备试试
- 百度一下试试https://baidu.com

**如何在群里提问**

- 把后台报错日志截图，并准备好充足的问题描述(态度要好)
- 将后台报错日志截图和完整的问题描述发到群里。
- 等待有人为你解答

<img src="picture/wenti/wenti2.png" width="50%">

<img src="picture/wenti/wenti1.png" width="50%">

## 1. cookie 绑定失败？

- 先把云崽 `#强制更新` 一下 
- 然后重新获取cookie
- 实在不行就把云崽删了。

## 2. 装完 node 但是还是提示 `npm:command not found`

- 没配置环境变量而已
- 请自行百度搜索 `Windows环境变量设置`
- 修改完重启电脑即可食用

## 3. 签到显示 `验证码失败` ?

- 问得好，好问题
- 太正常不过，这个问题无解，有解决方法的请私发我
- 至于什么时候会好嘛，我也不知道，你问大伟哥去

## 4. 提示 `qq版本过低` ？

- 方法1:

- <img src="picture/wenti/qq.png" width="50%"> <br>此图来源于喵喵插件群

- 记得多试几次
- 亲测有效
- 只改imei即可，若无法解决可全改。
- 不建议**一直尝试登录。**
- 方法2:**切换登录协议ipad-安卓手机-安卓手表**
- 方法3:**使用gocq获取token登录https://b23.tv/l78kDjj**
- 方法4:**https://github.com/MrXiaoM/Aoki**
- 方法5:**玩云崽死路一条，去你****的Oicq**
- 方法6:**linux使用rm -rf Yunzai-Bot/,Windows请右键Yunzai-Bot文件夹选择删除.**
- 方法7:**玩nonebot2**
- 方法8:**换icqq**

## 5. 提示 `请配置公共ck` ？

- 字面意思，`#配置公共ck`然后把你的ck发给机器人
- 或者`#使用全部ck`

## 6，公共 ck 查询次数已用完，暂无法查询新 uid？

- 不用慌，再绑定一个就是了
- 或者 `#使用全部ck`

## 7. <img src="picture/wenti/redis.png" width="50%"> <br> MISCONF Redis is configured to save RDB snapshots

- 控制面板->系统和安全->系统->高级系统设置->高级选项卡下方第一个卡片“性能”里的设置按钮->高级选项卡->虚拟内存->更改->勾选最上方自动管理所有驱动器的分页文件大小->重启电脑

## 8. 把机器人拉进群自动退了怎么办？

- 锅巴插件->配置管理->其它->退群人数改成 0 就行

## 9. 怎么删除插件?

- 在 `Yunzai-bot/plugins` 文件夹里找到对应的插件右键删除即可，
- 注：如果是插件包需要把整个文件夹都删掉

## 10. 怎么关闭云崽自带的入群欢迎?

- 在 `Yunzai-bot/plugins/example` 文件夹里找到入群欢迎插件，右键删除，或者在锅巴插件中进行配置

## 11. 显示机器人被冻结之类的怎么办？

- 号封了而已，没啥好办法，能解封就解不能解可以多备几个小号。关闭私聊，减少冻结频率。

## 12. xx 功能报错，xx 功能异常？

- 重装吧兄弟
- 也可以不重装：重置云崽步骤(数据会保留)：在云崽根目录下打开 git bash 输入`git pull`，然后再`git reset --hard origin/main`，最后再手动重启即可解决。

## 13. 喵喵插件的 `xx照片` 功能用不了？

- 把 `Yunzai-Bot/plugins/miao-plugin/resources` 的 `character-img` 文件复制一份到 `Yunzai-Bot/plugins/miao-plugin/resources/miao-res-plus` 里就好了

## 14. 机器人群聊消息发不出去，但是私聊正常？

- 这是触发了 QQ 的群聊风控，私聊机器人发送 <https://accounts.qq.com/safe/message/unlock?lock_info=5_5> 然后拿出你的手机，并登录机器人的手机 QQ，从机器人的手机 QQ 里打开个链接，验证就行了。

## 15. 十连次数怎么修改？

- 可以在锅巴插件里修改
- 有能力的可自行修改配置文件

## 16. 有没有便宜的服务器

- 服务器都挺贵的，一般只有新用户和购物节会特别便宜，所以大家各凭本事吧，反正只要是台能联网的就能搭这个机器人。
- 这里我推荐:[☞天梦阁互联](https://idc.qingvps.cn/)

## 17. 还有别的插件吗

- 更多的插件都在云崽官方群里，但是官方群它不对外开放...
- 或者你可以学学自己写插件
- 不会？，那就看插件编写教程吧


## 18.`QQ版本过低`  `登录失败，建议升级最新版本后重试，或通过问题反馈与我们联系。` `当前网络不稳定，登录失败。推荐使用常用设备或通过手机号登录。`
 
**换源法**
1. 先执行

```sh
git remote set-url origin https://gitee.com/yoimiya-kokomi/Yunzai-Bot.git && git checkout main && git pull
```

2. 再执行

```sh
 git reset --hard origin/main
```

3. 然后装下依赖

```sh
pnpm install -P
```

4. 进入`Yunzai-Bot\data`，找到自己的**QQ 号文件夹**，与 **device.json** 把这两个东西删掉
5. `node app` 正常启动云崽即可，目前**必须使用密码登录**，输入
```sh
npm run login
```
- 可以修改登录方式，并且如果遇到密保验证的话，请选择**短信验证码**验证
- **如果还登不上,建议换个号**

## 19.提示 puppeteer chromium 启动失败？Chromium 实例关闭或崩溃？

1. 先执行
```sh
pnpm config set puppeteer_download_host=https://npmmirror.com/mirrors
```
2. 再执行
```sh
node ./node_modules/puppeteer/install.js
```
## 20.redis 数据库打不开怎么办？

- 建议重装redis数据库