## 安装git

### windows安装git
从这个地址下载[https://git-for-windows.github.io/](https://git-for-windows.github.io/),直接exe安装即可。和其他软件安装一样的过程。
有时候我们安装其他工具，比如vs2017,github这些软件，默认都会带git的。可以使用everything查找下，本机是否安装过文件。
### linux安装git
```bash
[root@centos6 ~]# yum install git -y
```

### 按照后的配置
```bash
[root@centos6 ~]# git config --global user.name "zhaojiedi1992"
[root@centos6 ~]# git config --global user.email "zhaojiedi1992@outlook.com"
```
注意：windows确保git的命令路径添加到环境变量里面去。