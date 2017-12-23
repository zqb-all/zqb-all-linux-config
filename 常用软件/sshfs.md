sshfs, 用于挂载远程服务器的目录

将当前用户加入fuse组
```bash
sudo usermod -a -G fuse
```

假设远程服务器为192.168.12.34,用户名为zhuangqiubin,打算将远程的~/workspace挂载到本地的~/workspace

使用密码挂载
```bash
sudo sshfs -o allow_other  -o uid=1001 -o gid=1000  -o transform_symlinks -o follow_symlinks -o cache=no zhuangqiubin@192.168.12.34:/home/zhuangqiubin/workspace/  /home/pld/workspace/zhuangqiubin/workspace/
```

使用key
```
ssh-copy-id zhuangqiubin@192.168.12.34 （仅需做一次）
sudo sshfs -o allow_other,IdentityFile=/home/zhuangqiubin/.ssh/id_rsa  -o uid=1000 -o gid=1000  -o transform_symlinks -o follow_symlinks -o cache=no  zhuangqiubin@192.168.12.34:/home/zhuangqiubin/workspace /home/zhuangqiubin/workspace/
```

注意，此处的参数中，显示关闭了cache。使能cache可以提升一点性能，但可能导致本地跟远程的文件不一致，带来一些麻烦
