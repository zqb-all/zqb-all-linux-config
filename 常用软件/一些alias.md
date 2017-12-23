有些东西直接写在~/.bashrc中，在此列一下

## 退出多层目录

退出多层目录,简单粗暴
```bash
alias b1='cd ..'
alias b2='cd ../..'
alias b3='cd ../../..'
alias b4='cd ../../../..'
alias b5='cd ../../../../..'
alias b6='cd ../../../../../..'

```
## 打开文件管理器

有时候在shell中进入某个目录后，想用图形界面操作这个目录的东西，那就需要文件管理器

ubuntu使用nautilus作为文件管理器，记不住也不方便敲，做个好记的alias

```bash
alias opendir='nautilus'
```
生效后，在shell中直接使用
```bash
opendir .
```

## 打开各种东西
更强大的打开,xdg-open是用来打开Linux文件的命令,xdg-open会选择合适的程序打开指定文件，跟双击打开效果一样。
```bash
alias dakai='xdg-open'
```
加了这个后，上面那条opendir就基本就不需要了，碰到什么都是使用"dakai",如：
```bash
dakai .
dakai aaa.pdf
```


