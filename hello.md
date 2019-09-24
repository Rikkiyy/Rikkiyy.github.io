# Rikkiyy.github.io
Rikki'sblog
---
title: Welcome to my blog
categories: test
tags: tset

---

  这是我建立博客后写的第一篇小文章，按照惯例还是要记录一下建站的小过程滴。

###### 首先，我要有一个教程。

_~~<u>[这是在萌新必读里看到的一个随意的教程](https://segmentfault.com/a/1190000017986794 "这是在萌新必读里看到的一个随意的教程")</u>~~_  
根据教程确定了大概的步骤：
* 准备环境
* 安装hexo
* 注册github
* 配置ssh key
* 部署到github
* 现在在写博客哟～

###### 接下来，就是跟着教程操作啦，在这里我会记录一下实际操作过程中遇到的问题以及我的收获
1.  准备环境主要是为了安装hexo。这里我曾搜索了一下，hexo是一种轻量级博客框架，相对来说配置比较简单。
    很多人比较倾向于用Git+Github+Markdown+hexo的博客搭建方案，况且是for free。
    另外一种免费的且常用的方案是采用了Jekyll 框架，但好像因为一些原因安装出现阻力。。。
    安装git和node以及npm都无问题，第一个问题出现在安装hexo-cli的命令上：
    ```npm install -g hexo-cli```
    因为我是通过软件管理器从默认软件仓库安装的 Node.js 。所以出现了一些权限问题，在官网上看到了两种解决方案（但不要用sudo）一种是使用节点版本管理器重新安装npm（这个是网站更推荐的方式，hhh但我不知道为啥没操作成功采取了第二种），另一种是手动更改npm的默认目录：  
    <img src="/home/rikkiyang/myBlog/source/pictures/1.jpg" width="700">  

    更改后在使用该命令就解决了上一个问题，但弹出来了新的问题。

2.   用三行代码```hexo init myBlog ``` ```    cd myBlog ```   ```npm install```
     后就会新建我的myblog文件夹
     运行hexo s会弹出来一个http：//localhost：4000的链接 复制到浏览器即可看到预览的网站
     这个时候虽然生成了新的文件们，但是随之而来的还有许多警告们。
3.   注册github后我的第一件事不是立刻建立博客相关的仓库，而是<strong>学习了一下github的简单使用流程。</strong>  
     首先我建立了一个叫works的仓库,建立新的分支，刚好把我原始的readme内容填充为本周老师布置的java代码，然后保存更改，创建请求，合并拉取请求并删除临时建立的分支。  
     <img src="/home/rikkiyang/myBlog/source/pictures/3.jpg" width="500">  
     <img src="/home/rikkiyang/myBlog/source/pictures/4.jpg" width="800">    
     <img src="/home/rikkiyang/myBlog/source/pictures/13.png" width="800">

     这是相关的截图。
     后来又建立了以用户名开头以.github.io结尾的仓库为搭建博客做准备。
4.   接下来配置ssh key  
     什么是协议？ssh是何种协议？git采用了什么协议？  
     * 关于协议，接触最多的应该就是输入网址时的http，百度了一下：<u>_Web使用一种名为HTTP（HyperText Transfer Protocol，超文本传输协议）的协议作为规范，完成从客户端到服务器等一系列运作流程。而<strong>协议是指规则的约定</strong>。可以说，Web是建立在HTTP协议上通信的。_</u>HTTP最初的目的是为了让研究者共享知识信息，所以它的主要作用就是文档传输，它是一种用于传输文档的协议。  
     * 记得以前在输入http时同学让我输入https，说这样更安全，关于他们的区别，后来我也曾进行过比较：<u>HTTPS（全称：Hypertext Transfer Protocol over Secure Socket Layer），是以安全为目标的HTTP通道，简单讲是HTTP的安全版。即HTTP下加入SSL层，<strong>HTTPS的安全基础是SSL</strong>，因此加密的详细内容就需要SSL。 它是一个URI scheme（抽象标识符体系），句法类同http:体系。用于安全的HTTP数据传输。https:URL表明它使用了HTTP，但HTTPS存在不同于HTTP的默认端口及一个加密/身份验证层（在HTTP与TCP之间）。</u>https协议需要到ca申请证书，一般免费证书很少，需要交费。http是超文本传输协议，信息是明文传输，https 则是具有安全性的ssl加密传输协议http和https使用的是完全不同的连接方式用的端口也不一样,前者是80,后者是443。  
     * SSH的英文全称是Secure Shell。通过使用SSH，你可以把所有传输的数据进行加密，这样"中间人"这种攻击方式就不可能实现了， 而且也能够防止DNS和IP欺骗。还有一个 额外的好处就是传输的数据是经过压缩的，所以可以加快传输的速度。 SSH有很多功能，它既可以代替telnet，又可以为ftp、pop、甚至ppp提 供一个安全的"通道"。  
     * ssh与ssl的简称如此相似我也搜索了他们的区别。  
     相同点：他们都使用了非对称加密，将应用层进行了加密，另外，他们其实都是比较基础的应用层协议，即它们上面还可以再放其它应用层协议，如FTP协议等。  
     不同点：SSH不需要证书，即不需要公证机构，SSH实现了主机用户名和密码的认证，这是SSH的SSH-TRANS部分完成的，而SSL没有这个功能。  
     * Git 可以使用四种主要的协议来传输资料：本地协议（Local），HTTP 协议，SSH（Secure Shell）协议及 Git 协议。   

     因为之前电脑上生成过ssh key，使用```cat ~/.ssh/id_rsa.pub```命令即可查看ssh key  
     <img src="/home/rikkiyang/myBlog/source/pictures/5.jpg" width="500">  
5.   部署到github要先修改 _config.yml 配置文件配置参数，在生成的blog相关文件夹里。  
     <img src="/home/rikkiyang/myBlog/source/pictures/6.jpg" width="500">  

     在接下来的安装部署插件时 ```npm install hexo-deployer-git --save```又出了问题 大概有4，5个WARNING，最后被我反复修改变得只有两个，
     <img src="/home/rikkiyang/myBlog/source/pictures/2.jpg" width="700">  
-     <img src="/home/rikkiyang/myBlog/source/pictures/7.png" width="700">  

     最后两个直接忽略掉。又百度到了新的教程_~~<u>[一个很多错误情况都涵盖了但一般教程都没提到的无脑教程](https://blog.csdn.net/ibigboy/article/details/90480376 "一个很多错误情况都涵盖了但一般教程都没提到的无脑教程")</u>~~_    
     其中出现问题也都基本一致，下面截几张图走个流程。。。  <img src="/home/rikkiyang/myBlog/source/pictures/8.png" width="700">  

    <img src="/home/rikkiyang/myBlog/source/pictures/9.jpg" width="700"> 这里认真看了提醒
- <img src="/home/rikkiyang/myBlog/source/pictures/10.jpg" width="700">  
  <img src="/home/rikkiyang/myBlog/source/pictures/11.png" width="700">    
  <img src="/home/rikkiyang/myBlog/source/pictures/12.png" width="700">  

    至此我的博客就差不多了。   

###### 一句话的感悟  
  感谢这次活动，让我好好体验了一把自己探索的乐趣，也许会有很多问题，但自己搜索真的比让别人帮忙爽多了hhhh还有就是不能盲目的看教程，出现的问题也要多想想多查一查这样才能解决问题。
