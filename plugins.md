# Yunzai-Bot插件编写教学

- 推荐使用VCcode编写[☞下载][vccode]
 
## 单个的js插件

- [oicq][oicq]
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
