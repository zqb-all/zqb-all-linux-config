常用grep搜索，命令为
```bash
grep  xxx  . -nrI
```

建立~/.mygrep.sh，添加gep函数。本来是叫gp的，后来跟zsh中的git插件冲突，就改为gep。

```bash

gep() {
	grep -rnI "$1" "${2:-.}"  --exclude tags;
}
```

在.bashrc中添加
```bash
. ~/.mygrep.sh

```



