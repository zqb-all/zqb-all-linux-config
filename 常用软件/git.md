代码版本管理

## git常用命令
git需要掌握一些常用命令

## gitconfig配置文件
git 的一些配置，会保存在~/.gitconfig文件中

## git配置alias
对于常用命令，可以配置一些缩写，简化使用

如,在git配置文件中添加如下设置
```bash
[alias]
	df = diff --ignore-space-at-eol
	fp = format-patch --ignore-space-at-eol -M -C
	fpb = "!f(){ git format-patch --ignore-space-at-eol -M -C --subject-prefix="PATCH][$(basename $PWD)/$(basename $(git config --get branch.$(basename $(cat .git/HEAD|awk '{print $2}')).merge))" ${*};};f"
	st = status
	br = branch
	ci = commit
	last = log -1 HEAD
	co = checkout
	cp = cherry-pick
	lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

```

```bash
git lg
```
一般我用这条命令来查看历史，缩减到一行并进行了一些格式化
```bash
git df
```
直接使用git diff其实敲起来也很顺手，这里主要是加了个参数，使git diff打印出相对路径，方便下一步进行编辑

其他的就不多解释了






