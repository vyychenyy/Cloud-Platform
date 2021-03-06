# 本地运行Hubot

### 安装nodejs
ubuntu 使用命令行进行安装

`sudo apt-get install nodejs`

`sudo apt-get install npm`

若在安装过程中出现无法定位软件安装包的问题，则使用如下语句解决：

`sudo apt-get update`

使用 如下语句 查询 node 的版本

`node --version`

我们使用的是V8.11.4

在安装过程中出现了npm ERR! cb() never called!

npm ERR! This is an error with npm itself. Please report this error at:
npm ERR!     <https://github.com/npm/npm/issues>
的问题

清除缓存：

`sudo npm cache clear --force `
### 安装Hubot

Hubot是基于node.js技术体系，使用CoffeeScript语言开发的开源chatbot。
要安装Hubot，
安装好node.js后，npm也会自动安装上，我们要使用npm来安装Hubot生成器。

`npm install -g yo generator-hubot` 

之后可以再任意的文件夹生成自己的Hubot，只要输入`yo hubot`即可。
生成时要注意，为了之后能够连接Slack，需要在adapter一栏打上slack，这样Hubot就安装完毕了。

### 启动并调试Hubot
在命令行输入下面的指令，就可以执行Hubot了

`bin\hubot.cmd`

注意这是windows环境下，如果是linux

`bin/hubot`

当你看到  

```
yourHubotName> 
```

这就表示你成功执行你的Hubot了，这里yourHubotName是在生成Hubot时给它取的名字。
Hubot有一些它自带的基础命令，比如输入yourHubotName ping，它会回你pong

```
yourHubotName> youHubotName ping
yourHubotName> PONG
```

### 开发自定义机器人脚本
Hubot的项目结构
- bin/ Hubot运行脚本
- node_modules/ 引用的包文件
- scripts/ 存放自定义脚本
- external-scripts.json 引用的外部脚本
- package.json 项目全局配置信息

我们的自定义脚本既可以使用CoffeeScript，也可以使用纯JavaScript来编写。
详细的说明可参考以下链接  
[https://hubot.github.com/docs/scripting/][1]

# 连接Hubot和Slack
要连接Hubot和Slack，首先要把Slack的adapter集成进来，输入以下命令

`npm install hubot-slack --save`

然后每次连接前，都需要把Hubot的API Token设好，在windows下输入以下指令

`set HUBOT_SLACK_TOKEN=xoxb-576609764288-580486290854-Pv8ovA0LcIZwTzlqNXXHVe6v`

Slack的Hubot API Token在Slack的Hubot的Setting里面可以找到

启动Hubot时，要声明使用的adaper是Slack

`bin\hubot.cmd -a slack`

在linux下，输入以下指令，一次性设置好API Token并启动Hubot

`env HUBOT_SLACK_TOKEN=xoxb-576609764288-580486290854-Pv8ovA0LcIZwTzlqNXXHVe6v ./bin/hubot --adapter slack`

这样启动后，就已经连接上Hubot了，之后可以在Slack跟我们的Hubot聊天啦

# 安装ansible

检查ansible的安装版本
`ansible --version`


# 利用ansible实现基本的操作
# 连接hubot和ansible



在linux下，在hubot项目下输入运行：
```
npm install hubot-ansible-me --save
```

然后在`external-scripts.json`中加入以下信息：
```
[
"hubot-ansible-me"
]
```
TIP: *不要忘记在之前的末尾添加`,`*

参考文档连接：[https://github.com/willdurand/hubot-ansible][2]



# Telegraf+Influxdb+Grafana构建监控平台
` wget https://dl.influxdata.com/influxdb/releases/influxdb_1.0.2_amd64.deb
sudo dpkg -i influxdb_1.0.2_amd64.deb
sudo systemctl start influxdb`

`wget https://dl.influxdata.com/telegraf/releases/telegraf_0.11.1-1_amd64.deb
sudo dpkg -i telegraf_0.11.1-1_amd64.deb
sudo systemctl start telegraf`

` wget https://grafanarel.s3.amazonaws.com/builds/grafana_3.1.1-1470047149_amd64.deb
sudo apt-get install -y adduser libfontconfig
sudo dpkg -i grafana_3.1.1-1470047149_amd64.deb
systemctl start grafana-server `

参考文档链接[https://www.cnblogs.com/renqiqiang/p/8659772.html][3]




[1]: https://hubot.github.com/docs/scripting/
[2]: https://github.com/willdurand/hubot-ansible
[3]:https://www.cnblogs.com/renqiqiang/p/8659772.html

# Nginx搭建图片服务器
https://www.cnblogs.com/shuaifing/p/8268949.html
https://blog.csdn.net/u012809062/article/details/70307130

### flask 环境
http://www.pythondoc.com/flask/installation.html#installation
