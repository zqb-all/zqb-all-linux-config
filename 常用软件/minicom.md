minicom是一个简单的串口软件

## 安装
```bash
sudo apt-get install minicom
```


## 使用方式
```bash
minicom -s 进行配置
minicom 按默认参数打开
```

## 退出方式
按下Ctrl+A，再按下C

## 暂停
输出太多太快时，可按"Ctrl+A"达到暂停窗口刷新的效果

## 一些参数
加上 -C 可以指定记录的文件

加上 -D 可以指定要打开的串口设备

## 包装脚本
每次手工选择要打开的串口比较麻烦，可以使用脚本

建立~/.myminicom.sh，内容如下

```bash
com() {
	ports_USB=$(ls /dev/ttyUSB*)
	ports_ACM=$(ls /dev/ttyACM*)  #arduino
	ports="$ports_USB $ports_ACM"
	datename=$(date +%Y%m%d-%H%M%S)
	select port in $ports;do
		if [ "$port" ]; then
		    echo "You select the choice '$port'"
		    minicom -D "$port" -C /tmp/"$datename".log "$@"
		    break
		else
		    echo "Invaild selection"
	    fi
	done
}
```
添加到~/.bashrc中
```bash
source ~/.myminicom.sh

```
需要的时候，输入"com"即可调用
```bash
com
```

log默认保存到/tmp目录下，如果需要指定特定的log保存文件，则使用-C参数，如
```bash
com -C mylog.txt
```
