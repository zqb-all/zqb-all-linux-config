目前使用的终端

##Guake3
###Guake3说明
Guake 在2018年被移植到了GTK3, 由于新的Guake是基于GTK3和Python3,开发人员决定跳过版本号1.x和2.x,直接升级到Guake 3.

基于GTK2的旧版本，则被放到了分支0.8.x中，并不再维护。

源码: [github](https://github.com/Guake/guake)

官方主页: [guake-project](http://guake-project.org)

在线文档: [ReadTheDocs](http://guake.readthedocs.io/)

协助翻译: [weblate](https://hosted.weblate.org/projects/guake/guake/)

###安装
官方安装说明位于[Readthedocs](https://guake.readthedocs.io/en/stable/user/installing.html)

####Debian / Ubuntu
```bash
sudo apt-get install guake
```
####Pypi
Guake现在会自动发布到Pypi.可使用pip安装
```bash
pip install --user guake
```
注意，需要将以下路径加入到环境变量PATH中
```bash
$HOME/.local/bin
```
####从源码安装
下载源码
```bash
git clone https://github.com/Guake/guake.git
```
安装依赖(Python,GTK,VTE等)

可以使用源码中附带的脚本来安装依赖
```bash
 ./scripts/bootstrap-dev-[debian, arch, fedora].sh run make
```
安装命令
```bash
make
sudo make install
```
卸载命令
```bash
make
sudo make uninstall
```
重新安装命令
```bash
sudo make uninstall && make && sudo make install
# 或使用如下简写:
make reinstall  # (do not sudo it!)
```
###问题及解决
在ubuntu16.04上安装后，启动时，报
```bash
[ERROR] Unable to start Guake, missing mandatory dependency: Keybinder 3
```
通过如下命令解决
```bash
sudo apt-get install gir1.2-keybinder-3.0
```

在启动时，报错，其中有些路径包含了python2.7字样

解决方式,编辑
```bash
~/.local/bin/guake
```
将第一行的
```bash
#!/usr/bin/python
```
改为
```bash
#!/usr/bin/python3
```

##官方介绍

先从官方搬运一些介绍过来 http://guake-project.org/

### 简介
Guake 是一个Gnome下拉式终端，主要受到了Quake中使用的著名终端的启发。

你可以通过一个按键，即时显示和隐藏终端，执行一个命令，然后返回到之前的任务，而不会中断工作流程。

### 无处不在

终端无处不在，只需要快捷键即可出现。

想象一下，你正在使用你最喜欢的文本编辑器，并且想要执行一些命令，比如执行你的代码的单元测试，检查一个手册页，或者编辑一些配置文件。您可以在不离开键盘的情况下以闪电般的速度进行。只需按下预定义的“显示Guake”热键，执行命令，然后隐藏终端并返回到工作状态。

### 简单优雅
使用compiz透明度和显示动画，将终端平滑地集成到GNOME环境中。

### 多显示器
Guake支持多显示器设置。可以在鼠标所在的显示器或专用的显示器上打开。

### 多选项卡
使用多个命名选项卡，可以用命令设置名称，或手动修改。

### 快速打开
在你的终端输出中看到一个文件名？只需点击它，它将直接在你最喜爱的文本编辑器中打开。如果你的编辑器支持，甚至可以滚动到特定的行和列。

### 自动配置
在登陆时自动启动Guake，并定义一个将在Guake启动时自动执行的脚本，以配置Guake的标签。
### 大量配色
提供了130多种预定义的配色，在选择最适合你的配色之前，可以进行预览。

### 安装方式
可查看release页面 https://github.com/Guake/guake/releases

源码位于github https://github.com/Guake/guake

## 个人补充
### ubuntu源安装
```bash
sudo apt-get install guake
```
### 源码安装
推荐，可以用上最新的特性，同时可以自己修改一些东西。

### 快捷键设置
guake允许快捷键，可以配置自定义的显示热键，如我设置了F8，中指往上即可方便呼出使用

另外可以设置在标签页之间切换的快捷键，我设置了Alt+j Alt+k

### 自定义快速打开
对于guake提供的快速打开功能，非常好用

但默认的匹配规则还是太少，可以自己修改源码添加规则，如配置上对于git的规则，具体待补充


