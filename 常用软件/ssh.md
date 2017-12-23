ssh，用于远程登录

## 使用密码登录
假设远程服务器为 192.168.12.34，登录用户名为zhuangqiubin，密码为zqb1234

则使用 ssh  zhuangqiubin@192.168.12.34，按提示输入密码即可



## 使用key验证登录
每次登录都输入密码太麻烦了

使用ssh-keygen生成key

```bash
ssh-keygen
```
使用ssh-copy-id将key复制到远程服务器
```bash
ssh-copy-id zhuangqiubin@192.168.12.34
```
配置成功后，就不需要密码了

## 配置hostname
每次输入用户名和服务器地址，也很麻烦

在~/.ssh/config中可以添加如下配置

```bash
Host CS
hostname 192.168.12.34
user zhuangqiubin
```
配置成功后，可使用别名进行登录，如
```bash
ssh CS
```


## X11 forward
远程服务器没有系统剪贴板的话，可以使用X11 forward将本地的剪贴板共享过去

配合vim的设置，可以从远程vim中鼠标选中复制，粘贴到另一个vim或本地

```bash
Host CS
hostname 192.168.12.34
user zhuangqiubin
ForwardX11 yes
ForwardX11Trusted yes
```


