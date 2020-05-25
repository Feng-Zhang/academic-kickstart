[TOC]
# 前言
关于搭建一个博客或个人网站的好处不用我多说，但创建网站的难度可能会让人望而却步。本人从网络上获得过很多帮助，学到很多。很早就萌发了自己建网站并分享知识的想法，但是又不想在简书这类的网站上写作。原谅我是个拖延控，有时间就写一点，很可能一篇文章写好久，也不喜欢在网上编辑。此外，知识需要积累形成框架，由于平时我所有的笔记都放在有道云笔记中，复制粘贴到简书有时候格式不对，又不想进行二次编辑。最重要的是不够Geek（装逼）。

其实中间有过一段时间，利用hexo、github和github page创建过静态网站。但是用得不太顺手，原因有很多，比如：老是花时间在怎么改网页主题上，而不是专注在写作上；markdown（md）文件中的图片迁移很麻烦，网上的图片老是会丢失；github page 在国内打开很慢而且SEO不容易搜索到。因此，一直耽误到现在，其实一直贼心不死，想得到一个不太要维护，可以专注写作，文档可以同步（在别的电脑上也可以编辑），又很geek的网站。我的想法是把所有笔记保存在有道云笔记中进行维护和整理，需要分享的话可以在本地用typora写md文档同时又在有道云笔记中进行保存，md文档托管到git可以自动渲染成网页。为什么不直接用有道云笔记中的md呢？因为它要插入图片得是VIP,而且导出来的md文档没办法显示图片，此外有些版本还不支持导出md文件（如6.10.1.0版本）。最终我觉得搭网站最好的方式是hugo+github+Netlify。


其实有这想法的不只我一个，关于利用hugo和Github建网站的博客很多，但是有些博客内容有些出入，可能是由于英文翻译或版本更新所造成的。这里建议大家直接看hugo的[英文官网](https://gohugo.io/getting-started/quick-start/)和[hugo in action](https://livebook.manning.com/book/hugo-in-action/about-this-meap/v-4/)，或者[官方翻译](https://s0gohugo0io.icopy.site)同时网上的博客可以进行参考。这篇博客主要针对搭建过程中可能遇到的问题进行记录，希望对大家有所帮助。  

# 原理
那么如何用静态网页创建网站呢？很多博客一上来就直接讲方法，怎么一步步运行，得到一个简陋的网页。但是不知其所以然，因此这里想先介绍一下基本原理，方便理解和后面的debug。
1. 首先你得在本地生成静态网页文件。这里推荐用hugo或hexo。
2. 然后把静态网页文件托管到github仓库。这里推荐使用git和gitlab工具。
3. 把远程的静态网页文件进行渲染，形成让大家可根据网址直接阅览的网页。可用github page和Netlify.
4. 找到有道云笔记的md文件，用typora进行编辑，并用图床解决图片容易丢失问题。

关于hugo和hexo，github和gitlab，github page和Netlify的差别网上有很多博客，这里就不赘述了。目前我觉得最好的方式是：hugo+github+Netlify

# 快速入门

如果有相关静态网页生成的经历，可以直接忽略快速入门，直接到下一节：进阶。

## 1、本地生成静态网页文件
如果不想看英文的，可以参考[这篇](https://jdhao.github.io/2018/10/10/hexo_to_hugo/)和[这篇](https://mogeko.me/2018/018/)中文 。

下面简要阐述过程：  
```
hugo new site hugo
cd hugo
git init
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
echo 'theme = "ananke"' >> config.toml
hugo new posts/my-first-post.md
hugo server 
```
这时出现类似下面的信息，说明生成静态网页成功。可以在浏览器上输入 http://localhost:1313/ 进行浏览。  
```
Building sites …
                   | EN
-------------------+-----
  Pages            | 11
  Paginator pages  |  0
  Non-page files   |  1
  Static files     | 39
  Processed images |  0
  Aliases          |  2
  Sitemaps         |  1
  Cleaned          |  0

Built in 37 ms
Watching for changes in E:\blogs\hugo\{archetypes,content,data,layouts,static,themes}
Watching for config changes in E:\blogs\hugo\config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

如果出现下面的错误：  
```
hugo new posts/my-first-post.md
Error: "E:\blogs\quickstart\config.toml:3:1": unmarshal failed: Near line 3 (last key parsed ''): bare keys cannot contain '\x00'
```
这是因为E:\blogs\hugo\config.toml里面有一些NUL的间隔符，可能是由于echo的命令产生的。手动把它们删除就行了。


## 2、托管到github
把我们本地生成的静态网页托管到[github](https://github.com)上进行保存，而不用自己进行维护。  
首先在github上新建账号，并创建一个新的仓库，以仓库名为test为例。  

```
cd .\public
git init
git add .
git commit -m "update"
git remote add origin https://github.com/你的git账户/test.git
git push
```
这样就把东西上传到github上了。

## 3、用Netlify渲染网页
最后我们用[Netlify](https://www.netlify.com)对托管到github上的静态网页进行渲染。很简单可以看这篇[教程](https://kuleyu.github.io/hexolog/post/31808.html)。至此一个简陋的网页就建好了。但是可一点也不cool啊，客官别急，请看下面进阶教程。




# 进阶
## 1、添加主题
首先我们可以到[hugo主题库](https://themes.gohugo.io)中找一个自己喜欢的主题。我比较喜欢的一个主题是academic，B站上还有人介绍[Academic视频](https://www.bilibili.com/video/BV1Tt411g7jx?p=2)。
由于大部分主题都已经有站点所需要的各种文件夹，所以不用自己再建站点。直接clone下来，把主题换成子模块的就行。快速入门的什么的可以忘记了^_^。

```
git clone https://github.com/sourcethemes/academic-kickstart.git My_Website
cd My_Website
git submodule update --init --recursive
```

## 2、修改网页
然后根据[academic文档](https://sourcethemes.com/academic/docs/)进行修改，变成你自己喜欢的样式。

pass后面会添加内容。

## 添加评论
[评论系统](https://blu174.mail.live.com/default.aspx?id=64855&owa=1&owasuffix=owa%2f)



# 写作

## 1、图片管理
在md文档中插入的图片是一个麻烦事。一般来说有三种解决方案。如下所示

### 放置在static中
可以直接把图片放在static中，不过以后图片一多就麻烦了。如果后面想迁移什么的就太麻烦了。

### 利用page bundle
可以在post下面新建文件夹，重命名为你想要的博客名后新建md文件。这个md文档名称一定得是**index.md**，然后我们就可在同一目录下放置图片。md可以使用相对位置进行引用。

### 利用图床
这里利用picgo工具，把图片复制后，按一个快捷键就会自动上传到picgo内设置的图床上。  
[picgo教程](https://picgo.github.io/PicGo-Doc/zh/)支持8大图床。有域名的可以选七牛云，否则可以github（虽然慢了点）。

## 2、更新博客的流程
日后更新博客时就需要在本地的hugo\content\post文件夹中编辑新的md文件，并通过git指令同步到Github中，Netlify会检测Github中库的动态，并及时更新发布的网站内容。  
由于我所有的笔记都保存在有道云笔记中，所以我想把博客


## 3、在另一台电脑上写作

# 域名
到name.com购买域名。

# Debug

- push error
```
git push academic master
remote: Permission to Feng-Zhang/academic-kickstart.git denied to xiaofeng007.
fatal: unable to access 'https://github.com/Feng-Zhang/academic-kickstart.git/': The requested URL returned error: 403
```

控制面板-用户帐户-凭据管理器-找到git:https://github.com-编辑  
对这个凭据进行编辑，把要远程的账号和密码加上。 

![](https://raw.githubusercontent.com/Feng-Zhang/figures/master/blog/20200525210606.png)


