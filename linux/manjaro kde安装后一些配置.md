# 一些配置文件的路径和说明

> 标签： #linux; #manjaro; #kde; #代理;



> manjaro Kde 5.5.6

## 默认程序配置文件

```shell
~/.config/mimeapps.list
```

设置`chrome` 为默认浏览器的话，先把`firefox`设置为默认程序，然后修改上面文件里面的所有`firefox`替换成`chromium`，然后卸载`firefox`。



## shadowsocks的config文件

```shell
/etc/shadowsocks/socks.json
```

配置文件放在了这个位置，使用`systemctl`进行启动，比如：

```shell
systemctl start shadowsocks@socks
systemctl stop shadowsocks@socks
systemctl status shadowsocks@socks

```



## cow 将socks代理转成http https代理

配置文件：

```shell
~/.cow/rc
```

配置内容：

```shell
...
listen = http://127.0.0.1:7777
proxy = socks5://127.0.0.1:1080
...
```

这样，电脑的就有两个端口在做代理了。。。



配置环境变量：

```shell
export http_proxy = http://127.0.0.1:7777
export https_proxy = http://127.0.0.1:7777
```



这样使用命令行工具就可以翻墙访问了，例如：`curl www.google.com`



`cow`[github](https://github.com/cyfdecyf/cow)地址



## gdriver 同步google云盘

> 命令行同步google云盘的东西
>
> [github](https://github.com/prasmussen/gdrive)

先使用命令：

```she
gdriver about
```

认证帐号，命令会打印出一个`url`地址，访问地址，认证帐号，然后会出现一串`code`，把这个`code`复制粘贴到命令行，然后回车，过一会就会现实硬盘的信息。认证就搞定了。



配置文件：

```shell
~/.gdriver
```

