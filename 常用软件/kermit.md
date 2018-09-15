kermit是一个简单的串口软件

## 安装
```bash
sudo apt-get install ckermit
```

## 使用方式
```bash
minicom -s 进行配置
minicom 按默认参数打开
```

## 退出方式
按下Ctrl+\，再按下C可退出串口，进入kermit控制台
输入exit退出kermit

## 包装脚本
每次手工选择要打开的串口比较麻烦，可以使用脚本

建立~/.mykermit.sh，内容如下

```bash

kcom() {
	ports_USB=$(ls /dev/ttyUSB*)
	ports_ACM=$(ls /dev/ttyACM*)  #arduino
	ports="$ports_USB $ports_ACM"
	select port in $ports;do
		if [ "$port" ]; then
		    echo "You select the choice '$port'"
		    kermit -c -l "$port" -b 115200 "$@"
		    break
		else
		    echo "Invaild selection"
	    fi
	done
}
```
添加到~/.bashrc中
```bash
source ~/.mykermit.sh

```
需要的时候，输入"kcom"即可调用
```bash
kcom
```
