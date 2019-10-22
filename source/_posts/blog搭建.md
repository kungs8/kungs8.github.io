

由于 NightTeam 的域名是 nightteam.cn，所以这里官方博客使用了二级域名 blog.nightteam.cn，官方主页使用了根域名 nightteam.cn，现在两个站点都已经稳定运行在 GitHub Pages 上面了，大家如果感兴趣可以去看一下。

•NightTeam HomePage：https://nightteam.cn/

•NightTeam Blog: https://blog.nightteam.cn/

下面是两个站点的预览图：

![1570603508110](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570603508110.png)

![1570603520122](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570603520122.png)

这里的主页就是用一个基本的静态页面搭建了，没有什么技术含量。博客相对复杂一点，使用了 Hexo 框架，采用了 Next 主题，在搭建的过程中我就顺手把搭建的流程大致记录下来了，在这里扩充一下形成一篇记录，毕竟好记性不如烂笔头。

于是，这篇《利用 GitHub 从零开始搭建一个博客》的文章就诞生了。



## 准备条件

在这里先跟大家说一些准备条件，有些同学可能一听到搭建博客就望而却步。弄个博客网站，不得有台服务器吗？不得搞数据库吗？不得注册域名吗？没事，如果都没有，那照样是能搭建一个博客的。

GitHub 是个好东西啊，它提供了 GitHub Pages 帮助我们来架设一个静态网站，这就解决了服务器的问题。

Hexo 这个博客框架没有那么重量级，它是 MarkDown 直接写文章的，然后 Hexo 可以直接将文章编译成静态网页文件并发布，所以这样文章的内容、标题、标签等信息就没必要存数据库里面了，是直接纯静态页面了，这就解决了数据库的问题。

GitHub Pages 允许每个账户创建一个名为 {username}.github.io 的仓库，另外它还会自动为这个仓库分配一个 github.io 的二级域名，这就解决了域名的问题，当然如果想要自定义域名的话，也可以支持。

所以说，基本上，先注册个 GitHub 账号就能搞了，下面我们来正式开始吧。



## 新建项目

首先在 GitHub 新建一个仓库（Repository），名称为 {username}.github.io，注意这个名比较特殊，必须要是 github.io 为后缀结尾的。比如 NightTeam 的 GitHub 用户名就叫 NightTeam，那我就新建一个 nightteam.github.io，新建完成之后就可以进行后续操作了。

另外如果 GitHub 没有配置 SSH 连接的建议配置一下，这样后面在部署博客的时候会更方便。



## 安装环境

### 1.安装 Node.js

首先在自己的电脑上安装 Node.js，下载地址：https://nodejs.org/zh-cn/download/，可以安装 Stable 版本。

安装完毕之后，确保环境变量配置好，能正常使用 `npm` 命令。

### 2.安装 Hexo

接下来就需要安装 Hexo 了，这是一个博客框架，Hexo 官方还提供了一个命令行工具，用于快速创建项目、页面、编译、部署 Hexo 博客，所以在这之前我们需要先安装 Hexo 的命令行工具。

命令如下：

```
npm install -g hexo-cli
```

安装完毕之后，确保环境变量配置好，能正常使用 `hexo` 命令。



## 初始化项目

接下来我们使用 Hexo 的命令行创建一个项目，并将其在本地跑起来，整体跑通看看。

首先使用如下命令创建项目：

```
hexo init {name}
```

这里的 name 就是项目名，我这里要创建 NightTeam 的博客，我就把项目取名为 nightteam 了，用了纯小写，命令如下：

```
hexo init nightteam
```

这样 nightteam 文件夹下就会出现 Hexo 的初始化文件，包括 themes、scaffolds、source 等文件夹，这些内容暂且先不用管是做什么的，我们先知道有什么，然后一步步走下去看看都发生了什么变化。

接下来我们首先进入新生成的文件夹里面，然后调用 Hexo 的 generate 命令，将 Hexo 编译生成 HTML 代码，命令如下：

```
hexo generate
```

可以看到输出结果里面包含了 js、css、font 等内容，并发现他们都处在了项目根目录下的 public 文件夹下面了。

然后我们利用 Hexo 提供的 serve 命令把博客在本地运行起来，命令如下：

```
hexo serve
```

运行之后命令行输出如下：

```
INFO  Start processing
INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
```

它告诉我们在本地 4000 端口上就可以查看博客站点了，如图所示：

![1570603764949](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570603764949.png)

这样一个博客的架子就出来了，我们只用了三个命令就完成了。



## 部署

接下来我们来将这个初始化的博客进行一下部署，放到 GitHub Pages 上面验证一下其可用性。成功之后我们可以再进行后续的修改，比如修改主题、修改页面配置等等。

那么怎么把这个页面部署到 GitHub Pages 上面呢，其实 Hexo 已经给我们提供一个命令，利用它我们可以直接将博客一键部署，不需要手动去配置服务器或进行其他的各项配置。

部署命令如下：

```
hexo deploy
```

在部署之前，我们需要先知道博客的部署地址，它需要对应 GitHub 的一个 Repository 的地址，这个信息需要我们来配置一下。

打开根目录下的 _config.yml 文件，找到 Deployment 这个地方，把刚才新建的 Repository 的地址贴过来，然后指定分支为 master 分支，最终修改为如下内容：

```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: {git repo ssh address}
  branch: master
```

我的就修改为如下内容：

```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: git@github.com:NightTeam/nightteam.github.io.git
  branch: master
```

另外我们还需要额外安装一个支持 Git 的部署插件，名字叫做 hexo-deployer-git，有了它我们才可以顺利将其部署到 GitHub 上面，如果不安装的话，在执行部署命令时会报如下错误：

```
Deployer not found: git
```

好，那就让我们安装下这个插件，在项目目录下执行安装命令如下：

```
npm install hexo-deployer-git --save
```

安装成功之后，执行部署命令：

```
hexo deploy
```

运行结果类似如下：

```
INFO  Deploying: git
INFO  Clearing .deploy_git folder...
INFO  Copying files from public folder...
INFO  Copying files from extend dirs...
On branch master
nothing to commit, working directory clean
Counting objects: 46, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (36/36), done.
Writing objects: 100% (46/46), 507.66 KiB | 0 bytes/s, done.
Total 46 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), done.
To git@github.com:NightTeam/nightteam.github.io.git
 * [new branch]      HEAD -> master
Branch master set up to track remote branch master from git@github.com:NightTeam/nightteam.github.io.git.
INFO  Deploy done: git
```

如果出现类似上面的内容，就证明我们的博客已经成功部署到 GitHub Pages 上面了，这时候我们访问一下 GitHub Repository 同名的链接，比如我的 NightTeam 博客的 Repository 名称取的是 nightteam.github.io，那我就访问 http://nightteam.github.io，这时候我们就可以看到跟本地一模一样的博客内容了。

![1570603957626](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570603957626.png)

这时候我们去 GitHub 上面看看 Hexo 上传了什么内容，打开之后可以看到 master 分支有了这样的内容：

![1570604000195](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570604000195.png)

仔细看看，这实际上是博客文件夹下面的 public 文件夹下的所有内容，Hexo 把编译之后的静态页面内容上传到 GitHub 的 master 分支上面去了。

这时候可能就有人有疑问了，那我博客的源码也想放到 GitHub 上面怎么办呢？其实很简单，新建一个其他的分支就好了，比如我这边就新建了一个 source 分支，代表博客源码的意思。

具体的添加过程就很简单了，参加如下命令：

```
git init
git checkout -b source
git add -A
git commit -m "init blog"
git remote add origin git@github.com:{username}/{username}.github.io.git
git push origin source
```

如果这里的`git push origin source`报错：

![1570604189990](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570604189990.png)

出现这个问题是因为仓库地址不对，请执行下面的操作：

使用如下命令先查看一下：

![1570604284777](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570604284777.png)

发现跟github的地址不一致

![1570604379540](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570604379540.png)

然后在终端输入：

![1570604458235](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570604458235.png)

这里重新push成功了。

成功之后，可以到 GitHub 上再切换下默认分支，比如我就把默认的分支设置为了 source，当然不换也可以。



## 配置站点信息

完成如上内容之后，实际上我们只完成了博客搭建的一小步，因为我们仅仅是把初始化的页面部署成功了，博客里面还没有设置任何有效的信息。下面就让我们来进行一下博客的基本配置，另外换一个好看的主题，配置一些其他的内容，让博客真正变成属于我们自己的博客吧。

下面我就以自己的站点 NightTeam 为例，修改一些基本的配置，比如站点名、站点描述等等。

修改根目录下的 _config.yml 文件，找到 Site 区域，这里面可以配置站点标题 title、副标题 subtitle 等内容、关键字 keywords 等内容，比如我的就修改为如下内容：

```
# Site
title: 杭州师范大学大数据实验室
subtitle: 一个专注于科研前线的大数据团队，致力于打造更好更牛的大数据平台
description: 涉猎的主要编程语言为 Python、Java、Rust、C++、Go，领域涵盖爬虫、深度学习、服务研发和对象存储等。
keywords: "Python, Java, Rust, C++, Go, 爬虫, 深度学习, 服务研发, 对象存储"
author: yanpenggong
language: en
timezone: 
```

这里大家可以参照格式把内容改成自己的。

另外还可以设置一下语言，如果要设置为汉语的话可以将 language 的字段设置为 zh-CN，修改如下：

```
language: zh-CN
```

这样就完成了站点基本信息的配置，完成之后可以看到一些基本信息就修改过来了，页面效果如下：

![1570605466280](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570605466280.png)



## 修改主题

目前来看，整个页面的样式个人感觉并不是那么好看，想换一个风格，这就涉及到主题的配置了。目前 Hexo 里面应用最多的主题基本就是 Next 主题了，个人感觉这个主题还是挺好看的，另外它支持的插件和功能也极为丰富，配置了这个主题，我们的博客可以支持更多的扩展功能，比如阅览进度条、中英文空格排版、图片懒加载等等。

那么首先就让我们来安装下 Next 这个主题吧，目前 Next 主题已经更新到 7.x 版本了，我们可以直接到 Next 主题的 GitHub Repository 上把这个主题下载下来。

主题的 GitHub 地址是：https://github.com/theme-next/hexo-theme-next，我们可以直接把 master 分支 Clone 下来。

首先命令行进入到项目的根目录，执行如下命令即可：

```
git clone https://github.com/theme-next/hexo-theme-next themes/next
```

执行完毕之后 Next 主题的源码就会出现在项目的 themes/next 文件夹下。

然后我们需要修改下博客所用的主题名称，修改项目根目录下的 _config.yml 文件，找到 theme 字段，修改为 next 即可，修改如下：

```
theme: next
```

然后本地重新开启服务，访问刷新下页面，就可以看到 next 主题就切换成功了，预览效果如下：

![1570605664310](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570605664310.png)



## 主题配置

现在我们已经成功切换到 next 主题上面了，接下来我们就对主题进行进一步地详细配置吧，比如修改样式、增加其他各项功能的支持，下面逐项道来。

Next 主题内部也提供了一个配置文件，名字同样叫做 _config.yml，只不过位置不一样，它在 themes/next 文件夹下，Next 主题里面所有的功能都可以通过这个配置文件来控制，下文所述的内容都是修改的 themes/next/_config.yml 文件。

### 1.样式

Next 主题还提供了多种样式，风格都是类似黑白的搭配，但整个布局位置不太一样，通过修改配置文件的 scheme 字段即可，我选了 Pisces 样式，修改 _config.yml （注意是 themes/next/_config.yml 文件）如下：

```
scheme: Pisces
```

刷新页面之后就会变成这种样式，如图所示：

![1570605936702](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570605936702.png)

另外还有几个可选项，比如：

```
# scheme: Muse
#scheme: Mist
scheme: Pisces
#scheme: Gemini
```

大家可以自行根据喜好选择。

### 2.favicon

favicon 就是站点标签栏的小图标，默认是用的 Hexo 的小图标，如果我们有站点 Logo 的图片的话，我们可以自己定制小图标。

但这并不意味着我们需要自己用 PS 自己来设计，已经有一个网站可以直接将图片转化为站点小图标，站点链接为：https://realfavicongenerator.net[1]，到这里上传一张图，便可以直接打包下载各种尺寸和适配不同设备的小图标。

图标下载下来之后把它放在 themes/next/source/images 目录下面。

然后在配置文件里面找到 favicon 配置项，把一些相关路径配置进去即可，示例如下：

```
favicon:
  small: /images/favicon-16x16.png
  medium: /images/favicon-32x32.png
  apple_touch_icon: /images/apple-touch-icon.png
  safari_pinned_tab: /images/safari-pinned-tab.svg
```

配置完成之后刷新页面，整个页面的标签图标就被更新了。

### 3.avatar

avatar 这个就类似站点的头像，如果设置了这个，会在站点的作者信息旁边额外显示一个头像，比如我这边有一张 avatar.png 图片：

![1570606665407](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570606665407.png)

将其放置到 themes/next/source/images/avatar.png 路径，然后在主题 _config.yml 文件下编辑 avatar 的配置，修改为正确的路径即可。

```
# Sidebar Avatar
avatar:
  # In theme directory (source/images): /images/avatar.gif
  # In site directory (source/uploads): /uploads/avatar.gif
  # You can also use other linking images.
  url: /images/avatar.gif
  # If true, the avatar would be dispalyed in circle.
  rounded: true
  # If true, the avatar would be rotated with the cursor.
  rotated: true
```

这里有 rounded 选项是是否显示圆形，rotated 是是否带有旋转效果，大家可以根据喜好选择是否开启。

效果如下：

![1570606751856](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570606751856.png)

配置完成之后就会显示头像。

### 4.rss

博客一般是需要 RSS 订阅的，如果要开启 RSS 订阅，这里需要安装一个插件，叫做 hexo-generator-feed，安装完成之后，站点会自动生成 RSS Feed 文件，安装命令如下：

```
npm install hexo-generator-feed --save
```

在项目根目录下运行这个命令，安装完成之后不需要其他的配置，以后每次编译生成站点的时候就会自动生成 RSS Feed 文件了。

### 5.code

作为程序猿，代码块的显示还是需要很讲究的，默认的代码块我个人不是特别喜欢，因此我把代码的颜色修改为黑色，并把复制按钮的样式修改为类似 Mac 的样式，修改 _config.yml 文件的 codeblock 区块如下：

```
codeblock:
  # Code Highlight theme
  # Available values: normal | night | night eighties | night blue | night bright | solarized | solarized dark | galactic
  # See: https://github.com/chriskempson/tomorrow-theme
  highlight_theme: night bright
  # Add copy button on codeblock
  copy_button:
    enable: true
    # Show text copy result.
    show_result: true
    # Available values: default | flat | mac
    style: mac
```

修改前的代码样式：

![1570607137929](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570607137929.png)

修改后的代码样式：

![1570607324390](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570607324390.png)

嗯，个人觉得整体看起来逼格高了不少。

### 6.top

我们在浏览网页的时候，如果已经看完了想快速返回到网站的上端，一般都是有一个按钮来辅助的，这里也支持它的配置，修改 _config.yml 的 back2top 字段即可，我的设置如下：

```
back2top:
  enable: true
  # Back to top in sidebar.
  sidebar: false
  # Scroll percent label in b2t button.
  scrollpercent: true
```

enable 默认为 true，即默认显示。sidebar 如果设置为 true，按钮会出现在侧栏下方，个人觉得并不是很好看，就取消了，scrollpercent 就是显示阅读百分比，个人觉得还不错，就将其设置为 true。

![1570607790619](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570607790619.png)

具体的效果大家可以设置后根据喜好选择。

### 7.reading_process

reading_process，阅读进度。大家可能注意到有些站点的最上侧会出现一个细细的进度条，代表页面加载进度和阅读进度，如果大家想设置的话也可以试试，我将其打开了，修改 _config.yml 如下：

```
reading_progress:
  enable: true
  # Available values: top | bottom
  position: top
  color: "#222"
  height: 2pxreading_progress:  enable: true  # Available values: top | bottom  position: top  color: "#222"  height: 2px
```

设置之后显示效果如下：

![1570608199065](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570608199065.png)

### 8.bookmark

书签，可以根据阅读历史记录，在下次打开页面的时候快速帮助我们定位到上次的位置，大家可以根据喜好开启和关闭，我的配置如下：

```
bookmark:
  enable: true
  # Customize the color of the bookmark.
  color: "#222"
  # If auto, save the reading progress when closing the page or clicking the bookmark-icon.
  # If manual, only save it by clicking the bookmark-icon.
  save: auto
```

### 9.github_banner

在一些技术博客上，大家可能注意到在页面的右上角有个 GitHub 图标，点击之后可以跳转到其源码页面，可以为 GitHub Repository 引流，大家如果想显示的话可以自行选择打开，我的配置如下：

```
# `Follow me on GitHub` banner in the top-right corner.
github_banner:
  enable: true
  permalink: https://github.com/kungs8/kungs8.github.io/tree/master
  title: kungs GitHub
```

记得修改下链接 permalink 和标题 title，显示效果如下：

![1570608646950](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570608646950.png)

可以看到在页面右上角显示了 GitHub 的图标，点击可以进去到 Repository 页面。

### 10.gitalk

由于 Hexo 的博客是静态博客，而且也没有连接数据库的功能，所以它的评论功能是不能自行集成的，但可以集成第三方的服务。

Next 主题里面提供了多种评论插件的集成，有 changyan | disqus | disqusjs | facebook_comments_plugin | gitalk | livere | valine | vkontakte 这些。

作为一名程序员，我个人比较喜欢 gitalk，它是利用 GitHub 的 Issue 来当评论，样式也比较不错。

首先需要在 GitHub 上面注册一个 OAuth Application，链接为：https://github.com/settings/applications/new，注册完毕之后拿到 Client ID、Client Secret 就可以了。

首先需要在 _config.yml 文件的 comments 区域配置使用 gitalk：

```
# Multiple Comment System Support
comments:
  # Available values: tabs | buttons
  style: tabs
  # Choose a comment system to be displayed by default.
  # Available values: changyan | disqus | disqusjs | facebook_comments_plugin | gitalk | livere | valine | vkontakte
  active: gitalk
```

主要是 comments.active 字段选择对应的名称即可。

然后找打 gitalk 配置，添加它的各项配置：

```
# Gitalk
# Demo: https://gitalk.github.io
# For more information: https://github.com/gitalk/gitalk
gitalk:
  enable: true
  github_id: NightTeam
  repo: nightteam.github.io # Repository name to store issues
  client_id: {your client id} # GitHub Application Client ID
  client_secret: {your client secret} # GitHub Application Client Secret
  admin_user: germey # GitHub repo owner and collaborators, only these guys can initialize gitHub issues
  distraction_free_mode: true # Facebook-like distraction free mode
  # Gitalk's display language depends on user's browser or system environment
  # If you want everyone visiting your site to see a uniform language, you can set a force language value
  # Available values: en | es-ES | fr | ru | zh-CN | zh-TW
  language: zh-CN
```

配置完成之后 gitalk 就可以使用了，点击进入文章页面，就会出现如下页面：

![1570609778912](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570609778912.png)

GitHub 授权登录之后就可以使用了，评论的内容会自动出现在 Issue 里面。

### 11.pangu

我个人有个强迫症，那就是写中文和英文的时候中间必须要留有间距，一个简单直接的方法就是中间加个空格，但某些情况下可能习惯性不加或者忘记加了，这就导致中英文混排并不是那么美观。

pangu 就是来解决这个问题的，我们只需要在主题里面开启这个选项，在编译生成页面的时候，中英文之间就会自动添加空格，看起来更加美观。

具体的修改如下：

```
pangu: true
```

### 12.math

可能在一些情况下我们需要写一个公式，比如演示一个算法推导过程，MarkDown 是支持公式显示的，Hexo 的 Next 主题同样是支持的。

Next 主题提供了两个渲染引擎，分别是 mathjax 和 katex，后者相对前者来说渲染速度更快，而且不需要 JavaScript 的额外支持，但后者支持的功能现在还不如前者丰富，具体的对比可以看官方文档：https://theme-next.org/docs/third-party-services/math-equations。

所以我这里选择了 mathjax，通过修改配置即可启用：

```
math:
  enable: true

  # Default (true) will load mathjax / katex script on demand.
  # That is it only render those page which has `mathjax: true` in Front-matter.
  # If you set it to false, it will load mathjax / katex srcipt EVERY PAGE.
  per_page: true

  # hexo-renderer-pandoc (or hexo-renderer-kramed) required for full MathJax support.
  mathjax:
    enable: true
    # See: https://mhchem.github.io/MathJax-mhchem/
    mhchem: true
```

mathjax 的使用需要我们额外安装一个插件，叫做 hexo-renderer-kramed，另外也可以安装 hexo-renderer-pandoc，命令如下：

```
npm un hexo-renderer-marked --save
npm i hexo-renderer-kramed --save
```

另外还有其他的插件支持，大家可以到官方文档查看。

### 13.pjax

可能大家听说过 Ajax，没听说过 pjax，这个技术实际上就是利用 Ajax 技术实现了局部页面刷新，既可以实现 URL 的更换，有可以做到无刷新加载。

要开启这个功能需要先将 pjax 功能开启，然后安装对应的 pjax 依赖库，首先修改 _config.yml 修改如下：

```
pjax: true
```

然后安装依赖库，切换到 next 主题下，然后安装依赖库：

```
$ cd themes/next$ git clone https://github.com/theme-next/theme-next-pjax source/lib/pjax
```

这样 pjax 就开启了，页面就可以实现无刷新加载了。

另外关于 Next 主题的设置还有挺多的，这里就介绍到这里了，更多的主题设置大家可以参考官方文档：https://theme-next.org/docs/。

## 文章

现在整个站点只有一篇文章，那么我们怎样来增加其他的文章呢？

这个很简单，只需要调用 Hexo 提供的命令即可，比如我们要新建一篇「HelloWorld」的文章，命令如下：

```
hexo new hello-world
```

创建的文章会出现在 `source/_posts` 文件夹下，是 MarkDown 格式。

在文章开头通过如下格式添加必要信息：

```
---
title: 标题 # 自动创建，如 hello-world
date: 日期 # 自动创建，如 2019-09-22 01:47:21
tags: 
- 标签1
- 标签2
- 标签3
categories:
- 分类1
- 分类2
---
```

开头下方撰写正文，MarkDown 格式书写即可。

![1570610854702](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570610854702.png)

这样在下次编译的时候就会自动识别标题、时间、类别等等，另外还有其他的一些参数设置，可以参考文档：https://hexo.io/zh-cn/docs/writing.html。



## 标签页

现在我们的博客只有首页、文章页，如果我们想要增加标签页，可以自行添加，这里 Hexo 也给我们提供了这个功能，在根目录执行命令如下：

```
hexo new page tags
```

执行这个命令之后会自动帮我们生成一个 source/tags/index.md 文件，内容就只有这样子的：

```
---
title: tags
date: 2019-09-26 16:44:17
---
```

我们可以上面的后面自行添加一个 type 字段来指定页面的类型：

```
type: tags
comments: false
```

然后再在主题的 _config.yml 文件将这个页面的链接添加到主菜单里面，修改 menu 字段如下：

```
menu:
  home: / || home
  #about: /about/ || user
  tags: /tags/ || tags
  #categories: /categories/ || th
  archives: /archives/ || archive
  #schedule: /schedule/ || calendar
  #sitemap: /sitemap.xml || sitemap
  #commonweal: /404/ || heartbeat
```

这样重新本地启动看下页面状态，效果如下：

![1570611673655](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570611673655.png)

可以看到左侧导航也出现了标签，点击之后右侧会显示标签的列表。

## 分类页

分类功能和标签类似，一个文章可以对应某个分类，如果要增加分类页面可以使用如下命令创建：

```
hexo new page categories
```

然后同样地，会生成一个 source/categories/index.md 文件。

我们可以自行添加一个 type 字段来指定页面的类型：

```
type: categoriescomments: false
```

然后再在主题的 _config.yml 文件将这个页面的链接添加到主菜单里面，修改 menu 字段如下：

```
menu:  home: / || home  #about: /about/ || user  tags: /tags/ || tags  categories: /categories/ || th  archives: /archives/ || archive  #schedule: /schedule/ || calendar  #sitemap: /sitemap.xml || sitemap  #commonweal: /404/ || heartbeat
```

这样页面就会增加分类的支持，效果如下：

![1570611927105](C:\Users\Kungs\AppData\Roaming\Typora\typora-user-images\1570611927105.png)



## 搜索页

很多情况下我们需要搜索全站的内容，所以一个搜索功能的支持也是很有必要的。

如果要添加搜索的支持，需要先安装一个插件，叫做 hexo-generator-searchdb，命令如下：

```
npm install hexo-generator-searchdb --save
```

然后在项目的 _config.yml 里面添加搜索设置如下：

```
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```

然后在主题的 _config.yml 里面修改如下：

```
# Local search
# Dependencies: https://github.com/wzpan/hexo-generator-search
local_search:
  enable: true
  # If auto, trigger search by changing input.
  # If manual, trigger search by pressing enter key or search button.
  trigger: auto
  # Show top n results per article, show all results by setting to -1
  top_n_per_article: 5
  # Unescape html strings to the readable one.
  unescape: false
  # Preload the search data when the page loads.
  preload: false
```

这里用的是 Local Search，如果想启用其他是 Search Service 的话可以参考官方文档：https://theme-next.org/docs/third-party-services/search-services。

## 404 页面

另外还需要添加一个 404 页面，直接在根目录 source 文件夹新建一个 404.md 文件即可，内容可以仿照如下：

```
---
title: 404 Not Found
date: 2019-09-22 10:41:27
---

<center>
对不起，您所访问的页面不存在或者已删除。
您可以<a href="https://blog.nightteam.cn>">点击此处</a>返回首页。
</center>

<blockquote class="blockquote-center">
    NightTeam
</blockquote>
```

这里面的一些相关信息和链接可以替换成自己的。

增加了这个 404 页面之后就可以

完成了上面的配置基本就完成了大半了，其实 Hexo 还有很多很多功能，这里就介绍不过来了，大家可以直接参考官方文档：https://hexo.io/zh-cn/docs/ 查看更多的配置。

## 部署脚本

最后我这边还增加了一个简易版的部署脚本，其实就是重新 gererate 下文件，然后重新部署。在根目录下新建一个 deploy.sh 的脚本文件，内容如下：

```
hexo clean
hexo generate
hexo deploy
```

这样我们在部署发布的时候只需要执行：

```
sh deploy.sh
```

就可以完成博客的更新了，非常简单。

## 自定义域名

将页面修改之后可以用上面的脚本重新部署下博客，其内容便会跟着更新。

另外我们也可以在 GitHub 的 Repository 里面设置域名，找到 Settings，拉到下面，可以看到有个 GitHub Pages 的配置项，如图所示：

如图所示：

![null](https://mmbiz.qpic.cn/mmbiz_png/a0YItejHaTA1bncwcib5h56zF17LTYkiaMWRG8aN80Kia70H2EcOFvpFjOlKt7yk1hECUUJA46f0NtlW5rVJZHqzg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

下面有个 custom domain 的选项，输入你想自定义的域名地址，然后添加 CNAME 解析就好了。

另外下面还有一个 Enforce HTTPS 的选项，GitHub Pages 会在我们配置自定义域名之后自动帮我们配置 HTTPS 服务。刚配置完自定义域名的时候可能这个选项是不可用的，一段时间后等到其可以勾选了，直接勾选即可，这样整个博客就会变成 HTTPS 的协议的了。

另外有一个值得注意的地方，如果配置了自定义域名，在目前的情况下，每次部署的时候这个自定义域名的设置是会被自动清除的。所以为了避免这个情况，我们需要在项目目录下面新建一个 CNAME 文件，路径为 source/CNAME，内容就是自定义域名。

比如我就在 source 目录下新建了一个 CNAME 文件，内容为：

- 

```
blog.nightteam.cn
```

这样避免了每次部署的时候自定义域名被清除的情况了。

以上就是从零搭建一个 Hexo 博客的流程，希望对大家有帮助。