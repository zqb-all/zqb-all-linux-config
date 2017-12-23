minicom是一个简单的串口软件

## 一些参数
加上 -C 可以指定记录的文件

加上 -D 可以指定要打开的串口设备

## 暂停
输出太多太快时，可按"Ctrl+A"达到暂停窗口刷新的效果

## 包装脚本
每次手工选择要打开的串口比较麻烦，可以使用脚本

建立~/myminicom.sh

```bash
com() {
    ports=`ls /dev/ttyUSB*`
    select port in $ports;do
        if [ $port ]; then
            echo "You select the choice '$port'"
            minicom -D $port $@
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
