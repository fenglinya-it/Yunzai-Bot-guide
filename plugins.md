# 插件安装教程

- 注：均为V3插件

## [锅巴插件(Guoba-Plugin)](https://gitee.com/guoba-yunzai/guoba-plugin) 

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

## [喵喵插件 (miao-plugin)](https://gitee.com/yoimiya-kokomi/miao-plugin)

- Miao-Plugin是一个Yunzai-Bot的升级插件，提供包括角色查询等升级功能。

- 具体功能可在安装插件后 通过 #喵喵帮助 进行查看。如需进行设置可通过 #喵喵设置 命令进行管理。

- 推荐使用git进行安装，以方便后续升级。在Yunzai根目录夹打开终端，运行

-  使用gitee

```bash
git clone https://gitee.com/yoimiya-kokomi/miao-plugin.git ./plugins/miao-plugin/
```

- 进行安装。建议使用上述命令进行安装，以便于后续更新。 管理员发送`#喵喵更新`即可自动更新

## [抽卡插件 (flower-plugin)](https://gitee.com/Nwflower/flower-plugin)

- flower-plugin是一个适用于V3版本Yunzai-Bot的原神图鉴插件包，主要提供拓展抽卡功能，意在不修改本体抽卡卡池信息的情况下提供自定义卡池的拓展

- 在Yunzai-Bot根目录下，运行cmd，输入以下指令

```bash
git clone --depth=1 https://gitee.com/Nwflower/flower-plugin.git ./plugins/flower-plugin/
```

## py插件

- 我个人的建议是：
- 别去费精力装了
- 直接装个nonebot吧
- 换个登录端口实现1号俩机器人

## [单个js格式插件通用安装方法](https://gitee.com/yhArcadia/Yunzai-Bot-plugins-index#js%E6%8F%92%E4%BB%B6%E7%B4%A2%E5%BC%95example)

- 超级简单，只要把插件下载好后放入 `Yunzai-bot/plugins/example` 里即可 
<img src="picture/wenti/js-plugins.png" width="100%">

# Yunzai-Bot插件编写教学

# 前言
- 需要node.js基础,需要会使用redis数据库,
- 推荐使用VScode编写[☞下载](https://code.visualstudio.com/)
 
## 单个的js格式插件(example)

- [oicq文档](https://github.com/takayama-lily/oicq)
- 先新建一个文件，命名为Helloworld.js
- <u>命名可以改的，最好别用中文，改命名时要记得把下面的类名改了(大小写得一样)</u>

### 输出Hello，world！

- 代码示例

```javascript
//引入Yunzai插件功能
import plugin from '../../../../../lib/plugins/plugin.js'

//导出  类  类名===文件名 继承  插件类  
export class Helloworld extends plugin {
    constructor() {
        super({
            //后端信息
            name: 'Helloworld',//插件名字，可以随便写
            dsc: 'Helloworld',//插件介绍，可以随便写
            event: 'message',//这个直接复制即可，别乱改
            priority: 250,//执行优先级：数值越低越6
            rule: [
                {
                    //正则表达试
                    reg: '^#你好$',
                    //函数
                    fnc: 'Helloworld'
                }
            ]
        });
    };

    //函数
    async Helloworld(e) {
        e.reply("Hello, world!");//输出Hello，world！
        //阻止消息不再往下
        return;
    };
};
```

### reply函数的多种用法

1. 直接发送内容：

```javascript
    //发送内容:
    e.reply("Hello, world!");
```

2. 是否引用回复：

```javascript
//是否引用回复:
e.reply("Hello, world!", true);//false为不引用，true为引用
```

3. 群聊是否撤回消息：

```javascript
//群聊是否撤回消息:
e.reply("Hello, world!", false, { recallMsg: 5 });//最大120秒后撤回，0则不处理
```

4. 是否at用户:

```javascript
//是否at用户:
e.reply("Hello, world!", false, { recallMsg: 0 }, true);//false为不at用户，true为at用户
```

### 如何使用回复组件

- 代码示例

```javascript
//引入Yunzai插件功能
import plugin from '../../../../../lib/plugins/plugin.js'

//导出  类  类名:要与文件名一致 继承  插件类  
export class Helloworld extends plugin {
    constructor() {
        super({
            //后端信息
            name: 'Helloworld',//插件名字，可以随便写
            dsc: 'Helloworld',//插件介绍，可以随便写
            event: 'message',//这个直接复制即可，别乱改
            priority: 250,//执行优先级：数值越低越6
            rule: [
                {
                    //正则表达式
                    reg: '^#你干嘛诶哟$',
                    //函数
                    fnc: 'Helloworld'
                }
            ]
        });
    };

    //函数
    async Helloworld(e) {
        /** 设置上下文，后续接收到内容会执行hei方法 */
        this.setContext('hei');
        //发送消息
        e.reply("1+1=?");
    }

    //回复函数
    async hei(e) {
        //获取消息
        let xiaoxi = e.message;
        //判断消息
        if (xiaoxi == 3) {   //是
            //回复
            e.reply("回答正确")
            //结束上下文
            this.finish('hei')
        }
        else {               //否
            //回复
            e.reply("回答错误")
            //再次使用执行hei方法 
            this.setContext('hei')
        }
    }
};
```

### 各式的判断

预计...没有预计（开学随缘更新）


## 大型的插件包(plugin)

| 文件/文件夹 | 作用 | 是否可选 | 对应文章跳转 | 
| --- | --- | --- | --- |
| index.js | 导入apps里的单js插件 | 否 | [点我](#index) |
| apps/ | 存放单js插件的位置 | 否 | [点我](#apps) |
| data/ | 存放插件数据的位置,可存储到Yunzai-Bot自带的data文件夹 | 是 | [点我](#data) |
| resources/ | 可存放README所使用的图片之类的资源文件 | 是 | [点我](#resources) |
| config/ | 存放插件的配置文件 | 否 | [点我](#config) |
| model/ | 存放插件的封装文件 | 否 | [点我](#model) |
| guoba.support.js | 支持锅巴插件显示信息或配置(显示信息如不添加会是插件索引内的描述) | 是 | [点我](#锅巴支持) |
| .gitignore | 更新时不选中某些文件或文件夹 | 是 | [点我](#gitignore)

### index
- 此js会导入apps文件夹(你可以选中其他的)内的所有js文件
- 可添加载入提示

编写示例:
```javascript
//导入node:fs模块
import fs from node:fs

//输出提示
logger.info('更换为你需要的提示')
logger.info('更换为你需要的提示')
logger.info('更换为你需要的提示')
//如需更多可复制粘贴
//info可替换为: debug mark error

//加载插件
const files = fs.readdirSync('./plugins/你插件包的名字/apps').filter(file => file.endsWith('.js'))

let ret = []

files.forEach((file) => {
  ret.push(import(`./apps/${file}`))
})


ret = await Promise.allSettled(ret)

let apps = {}
for (let i in files) {
  let name = files[i].replace('.js', '')

  if (ret[i].status != 'fulfilled') {
      logger.error(`载入插件错误：${logger.red(name)}`)
      logger.error(ret[i].reason)
      continue
  }
  apps[name] = ret[i].value[Object.keys(ret[i].value)[0]]
}


export { apps }
```

### apps
- 可根据[上方教程](#Yunzai-Bot插件编写教学)进行编写单js插件并放置于apps

### data
- 存放插件需要长期储存的文件,可存放于Yunzai-Bot自带的data文件夹

例如:
```
data/xxxx/xxxx
```

### resources
- 存放插件的资源文件

例如:
```
data/README/img
data/README/document
data/common
data/help/help.html
data/help/help.css
```

### config
- 存放插件的配置文件
- 例如:
```
config/config.yaml
config/help.yaml
```

### model
- 存放插件的封装文件

例如:
```
config.js
help.js
setting.js
```

### 锅巴支持
- 支持锅巴插件显示信息或配置(显示信息如不添加会是插件索引内的描述)

- [编写示例](https://gitee.com/guoba-yunzai/guoba-plugin/blob/master/guoba.support.js)

### gitignore
- 更新时不选中某些文件或文件夹

语法:
```
空格不匹配任意文件，可作为分隔符，可用反斜杠转义
开头的文件标识注释，可以使用反斜杠进行转义
! 开头的模式标识否定，该文件将会再次被包含，如果排除了该文件的父级目录，则使用 ! 也不会再次被包含。可以使用反斜杠进行转义
/ 结束的模式只匹配文件夹以及在该文件夹路径下的内容，但是不匹配该文件
/ 开始的模式匹配项目跟目录
如果一个模式不包含斜杠，则它匹配相对于当前 .gitignore 文件路径的内容，如果该模式不在 .gitignore 文件中，则相对于项目根目录
** 匹配多级目录，可在开始，中间，结束
? 通用匹配单个字符
* 通用匹配零个或多个字符
[] 通用匹配单个字符列表
```

- 示例:
```
# 忽略所有data内的文件
data/*
# 忽略所有config内的文件
config/*
# 忽略resources/help/themes内的所有文件夹
resources/help/themes/**
# 选择resources/help/themes/default文件夹
!resources/help/themes/default/
# 忽略所有的.txt文件
*.txt
```