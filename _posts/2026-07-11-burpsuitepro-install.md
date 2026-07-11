# burpsuite专业版安装

### 准备工作

**去官网下载最新版的burpsiutepro版本**

[官方下载链接](https://portswigger.net/burp/releases#professional)

![image-20260611182437516](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260611182437516.png)

点击download，会下载一个安装脚本

![image-20260612151858706](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260612151858706.png)

给脚本执行权限，sudo chmode +x burpsuite_linux_v2026_4_3.sh，然后执行sudo ./burpsuite_linux_v2026_4_3.sh自动安装burpsuite

**下载激活工具**

激活工具是52网站上的大佬发的（[网站地址](https://www.52pojie.cn/thread-1953331-1-1.html)）打开网站里面有详细的介绍，如果感兴趣可以看看

这里直接给出[破解工具下载网站](https://github.com/Datch666/BurpKeygenCN)，打开网站下载最新版本BurpKeygenCN.jar，放到桌面如下图

![image-20260612152947151](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260612152947151.png)

### 激活

burpsuite安装完成后，进入burpsuite的安装目录，把BurpKeygenCN.jar放到/opt/BurpSuite

```shell
cd /opt/BurpSuite
mv ~/Desktop/BurpKeygenCN.jar /opt/BurpSuite
```

启动BurpKeygenCN.jar，java -jar BurpKeygenCN.jar

![image-20260711193724376](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711193724376.png)

运行后有一个界面，如果需要汉化就勾选，点击运行

![image-20260711194145611](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711194145611.png)

**将license点击复制然后ctrl+v粘贴进burp内**

![image-20260711194118489](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711194118489.png)

**点击手东激活（ps：如果是最新版本，在左下角可以找到手动激活）**

![image-20260711194342443](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711194342443.png)

**随后按照下图步骤将burp第二步给的秘钥粘贴进注册机 并将注册机生成的最后的秘钥粘贴进burp**

![image-20260711194434052](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711194434052.png)

**最后激活成功**

![image-20260711194507636](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711194507636.png)

### 设置一键启动

上诉虽然已经激活成功，但是，每次打开burpsuite，都要取/opt/BurpSuite，执行java -jar BurpKeygenCN.jar，太麻烦了。

写了一个shell脚本，把脚本放在/usr/local/bin，我们就能在终端直接输入脚本名字运行burpsuite了

~~~shell
cd /usr/local/bin
sudo vim burp

把下面内容复制到burp里面
------------------------------------------------------------------------
#!/bin/sh

# 关闭旧实例
pkill -f BurpKeygenCN.jar 2>/dev/null

# 启动新实例
exec nohup java -jar /opt/BurpSuite/BurpKeygenCN.jar >/dev/null 2>&1 &‘

------------------------------------------------------------------------
保存burp
chmod +x burp
~~~

最后在终端输入burp就能运行burpsuite了
