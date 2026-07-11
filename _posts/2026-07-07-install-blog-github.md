# GitHub个人博客搭建

### 博客基于jekll+github搭建

博客主题用的是github上面的jeyll主题，本文用的是[chirpy-starter](https://github.com/cotes2020/chirpy-starter/)。

下面是我搭建的博客[070’s blog](https://lkylin070.github.io/)

![image-20260711215331824](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711215331824.png)

### fork仓库

打开chirpy-starter(https://github.com/cotes2020/chirpy-starter/)，点击右上角Fork，Create a new fork

![image-20260711215645618](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711215645618.png)

进入fork的仓库，点击右上角settings

![image-20260711221648208](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711221648208.png)

修改Repository name，githubname.github.io，我的github用户是lkylin070，所以我的是lkylin070.github.io

![image-20260711222908830](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711222908830.png)

### 修改pages-deploy.yml

修改.github/workflows/pages-deploy.yml，远仓库的可能运行起来会有问题

直接把我仓库里面的pages-deploy.yml复制到你的仓库里面

这是我的pages-deploy.yml地址https://github.com/lkylin070/lkylin070.github.io/tree/master/.github/workflows/pages-deploy.yml

### 修改_config.yml

照着我的_config.yal填就好了，https://github.com/lkylin070/lkylin070.github.io/blob/master/_config.yml

把url改成自己的

![image-20260711233444709](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711233444709.png)

cdn也是换成自己的https://testingcf.jsdelivr.net/gh/自己的github名字/自己的github名字.github.io

avatar可以先空着，这是自己的博客头像，后面在assets里面上传一张图片

然后avatar: /assets/图片名字.png

![image-20260711233534075](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711233534075.png)

### 运行

点击settings，再点击左栏page，点击GitHub Actions，选择GitHub Actions

![image-20260711234113157](https://cdn.jsdelivr.net/gh/lkylin070/blogimage@main/img/image-20260711234113157.png)

等程序运行一会，然后访问https://自己的github名字.github.io，就能打开你的博客了

### git维护博客

> git安装和绑定自己的github，请自行再网上搜索

这里默认已经安装git和绑定自己的github，推荐再Linux里面使用，当然Windows也能用

准备好后拉取刚刚部署的博客仓库自己的

~~~git
git clone https://github.com/lkylin070/lkylin070.github.io.git
cd lkylin070.github.io
cd _posts
vim hello.md
~~~

 **_posts**是存放文章的地方，文章格式markdown，写好后放到里面就行

再hello.md，随便写点然后保存

最后，推送到github仓库就行，随后查看你的bolg就会看到你写的hello.md内容

~~~git
git add .
git commit -m "add hello.md"
git push
~~~

文章写的比较粗糙，本人水平有限，勿喷
