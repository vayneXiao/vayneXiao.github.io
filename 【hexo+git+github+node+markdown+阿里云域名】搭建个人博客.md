# 阿里云域名+hexo+git+github+node+markdown搭建个人博客

## 1，申请github账号
使用你的邮箱注册GitHub帐号：https://github.com/ 点击GitHub中的New repository创建新仓库，仓库名必须为：用户名.http://github.io 这个用户名使用你的GitHub帐号名称代替，这是固定写法，比如我的仓库名为vaynexiao.github.io，其他的不要动，点击Create repository

## 2，安装git和一段操作
安装很简单，一路next
桌面右击进入git bash，输入
git config --global user.name "你的github用户名"
git config --global user.email "你的github注册邮箱"
这相当于登录，然后输入
ssh-keygen -t rsa -C "你的github注册邮箱"
你会看到一个路径，在这个路径（.ssh文件夹中）下生成一个文件id.rsa.pub文件，将里面文本全部复制，打开https://github.com/settings/keys进行SSH keys设置，title随便填，key中粘贴你复制的密钥，点击Add SSH key
然后git bash中输入：
ssh git@github.com
如果出现
PTY.......
...
Connection to github.com closed.
说明成功。

## 3，安装node.js
下载LTS版本，一路next安装
然后在cmd中输入：
node -v
回车后是node.js的版本，在输入：
npm -v
是npm版本号

## 4，开始生成博客文件
在本地找一个路径新建一个Blog文件夹，然后后面的操作生成的文件全部在这里面
这该文件夹中按住shift右击，进行cmd，win10是powershell窗口，都行
使用npm安装hexo，输入：
npm install -g hexo-cli
需要耐心等待变化，几分钟不到吧，然后初始化博客，输入：
hexo init blog
也需要耐心等待，也是几分钟不到吧，
然后输入：
hexo new test_my_site
hexo g
hexo s
分别意思是：创建文章、生成网页、启动服务器
此时浏览器输入：
localhost:4000
就可看到我们的雏形博客了，如果打不开，可能是端口被占用，输入：
hexo server -p 5000 
更改端口为5000，可再次尝试

上面只是在本地预览，接下来要做的就是就是推送网站，也就是发布网站，让我们的网站可以被更多的人访问。在设置之前，需要解释一个概念，在blog根目录里的_config.yml文件称为站点配置文件，打开后进行修改：
这里用我的配置举例；我的用户名是vaynexiao
deploy:
  type:github
  repository:git@github.com:vayneXiao/vayneXiao.github.io.git
  branch:master

然后保存。 其实就是给hexo d 这个命令做相应的配置，让hexo知道你要把blog部署在哪个位置，很显然，我们部署在我们GitHub的仓库里。最后安装Git部署插件，输入命令：
npm install hexo-deployer-git --save
这时，我们分别输入三条命令：
hexo clean 
hexo g 
hexo d
其实第三条的 hexo d 就是部署网站命令，d是deploy的缩写。完成后，打开浏览器，在地址栏输入你的放置个人网站的仓库路径，即 http://xxxx.github.io
你就会发现你的博客已经上线了，可以在网络上被访问了。

## 5，绑定域名
申请阿里云账号（当然腾讯云，，等等其他的随你，都可以），进入控制台，
域名 - 信息模板
填好后，提交，等待一个工作日，后会通过，记住：照片要清晰，我当时就照片不清晰又重新审核了一天。
然后找到域名注册，输入你喜欢的域名，会出现很多后缀:
.com .cn .xyz
价格不等，随你挑选，申请时候要付钱，也要用到刚才注册的信息模板，这个又需要一天审核。
通过后，找到域名，点击解析，进去后添加记录，两个CNAME的记录类型，主机记录分别是@和www，记录纸填写你的github地址，比如我：vaynexiao.github.io
填好后进入你的github中其中一个项目页面，链接类似如下：
https://github.com/vayneXiao/vayneXiao.github.io
点击setting，往下拉，找到Github Pages底下的Custom domain输入你，买的域名
我的就是：vaynexiao.com
点击save

注意：阿里云中填好域名解析后需要10来分钟分配DNS，等一下就好。

