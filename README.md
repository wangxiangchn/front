### 前端入坑

#### node

在 [mac](http://44ux.com/index.php/tag/mac/) 下安装 [nodejs](http://44ux.com/index.php/tag/nodejs-2/) 相对来说是比较方便的，如果你之前安装过类似 [Macports](http://www.macports.org/install.php) 或者[homebrew](http://mxcl.github.com/homebrew/) 这样的工具，只需要简单的一句话就可以安装。如果使用的是 Macports，那么在终端执行如下命令即可：

```
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```

```
`brew ``install` `node`
```

如果使用的是 homebrew，则执行下面的命令即可安装：

```
`sudo port install nodejs`
```

如果你没有使用过这两个工具，建议去尝试使用一下，可以像 linux 下面的 apt-get 一样安装软件，非常方便。

如果你还没有使用过这两个工具，那么就只能手动安装了。Mac 下默认没有安装 gcc，无法直接从源码编译安装，laser 尝试了单独安装 gcc 的方法，没有成功。最好的建议是直接从 AppStore 下载安装 Xcode，安装之后常用的开发工具包就都有了。不过下载 Xcode 时间比较长，网速比较好的话可能也要 4 个小时以上。

安装好 Xcode 后，系统就有了 gcc 的功能，下面可以继续安装 [git](http://44ux.com/index.php/tag/git/)，从 Git clone 下来源码进行编译安装。关于 Git 是什么和如何安装 Git，网上已经有无数的资料，laser 这里就不再赘述了，推荐去看 [Github 的帮助文档](http://help.github.com/win-set-up-git/)，讲解很详细，只不过是英文的。从 Git 安装的步骤如下：

```
`git clone https:``//github``.com``/joyent/node``.git nodejs``cd` `nodejs``.``/configure``make``sudo` `make` `install`
```

等待命令成功执行即安装完成了。

如果你没有安装 Git，那么也可以直接[下载 nodejs 的源码 ](http://nodejs.org/#download)，解压缩后放到合适的路径，然后进入该文件夹，仍然执行：

```
`cd` `nodejs``.``/configure``make``sudo` `make` `install`
```

即可安装。



---



#### git

一、Git是一个分布式的代码版本管理工具。类似的常用工具还有SVN,CVS。最大的特点也是优点在于提供分布式的代码管理

1、分支代码只有一份！

使用过svn的童鞋想必都知道，当我们要开发一个新功能或者增加一个新版本或者修改一个复杂bug的时候，通常需要copy整份代码到本地一个目录，然后添加到svn服务器上进行代码管理。

而Git不同，Git可以创建许多branches，每个branch都是独立的，当我们需要修改代码的时候，commit也只是对本地仓库的修改。如果使用SourceTree,我们会发现在工具栏的Git Flow功能，已经很好的为此做了准备。

2、log在本地！

svn的log都是存储在服务器上的，当我们要查阅修改记录的时候，必须要能够连接上远程服务器，并且具有权限。而Git不同，Git对于本地仓库的修改记录都是在本地上的，方便查阅。

3、合并代码更加方便！

因为Git支持本地无限Branches，当我们个体在本地创建多个branches用于不同目的的时候（修改，新增，探索），合并一份代码显然要比svn合并一堆工程copy更加简单。

4、更加安全！

Git的commit命令不同于SVN，commit只是对本地仓库代码的一次更新。当需要提交到master远程仓库，或者其他远程分支仓库的时候，需要使用push功能。虽然增加了一个过程，却可以防止随意修改导致后期合并出现大问题的风险。 在用户工作的时候，从本地仓库修改文件（modified），写入git的暂存区域（staged），将暂存区域的内容提交到本地仓库（committed）。这一系列的工作都是在用户本机的本地仓库上进行的。当你将本地的仓库push到远程服务器上的仓库之前，远程仓库里是没有你的工作成果的。

5、目录更加简洁！

在Git本地仓库根目录，只有一个.git文件,它包含了所有的管理信息。而SVN想必大家都知道，每个子目录下都有噁心的.svn。这个当需要修改文件冲突等问题时，就需要考虑了。肯定是一个文件简单。

 

二、安装



在进行安装前，要说一下，Git和SVN一样，都需要创建一个服务器的，他们都可以创建自己的版本管理服务器。对于个人和小团队来说，使用托管服务器可能更合适。

常见的有Github 和 Bitbucket。Github没有个人免费仓库使用，代码放上去就是开源的。[Bitbucket](https://bitbucket.org/)的个人仓库相关页面已经基本汉化了。注册流程也比较简单。

MAC上最好的GIT免费GUI工具是[SourceTree](http://www.sourcetreeapp.com/)（没有之一）。此外，最好的GIT代码开源网站是[GitHub](https://github.com/)，最好的GIT代码私有库是[BitBucket](https://bitbucket.org/)。

安装过程：

1，下载Git installer，地址；<http://git-scm.com/downloads>

2，下载之后打开，双击.pkg安装

3， 打开终端，使用git --version或者which git命令查看安装版本，有就是安装成功了

4，创建一个全球用户名、全球邮箱

git config --global user.name "shengyao"

git config --global user.email "MY_NAME@example.com"

5、安装成功后打开终端

cd ~进入根目录

输入命令ssh-keygen生成ssh-key，如果有提示，一直按回车

6、将SSH key添加到GitHub。登录到GitHub页面，Account Settings->SSH Public Keys->Add another key

将生成的key(id_rsa.pub文件）内容copy到输入框中，save。

commd+shift+g进入/Users/chen/.ssh/就可以看得见私钥和公钥

私钥的名字是 id_rsa，是服务器确定你身份的唯一凭证。

公钥的名字是id_rsa.pub。把这个文件发给仓库管理员，仓库管理员会把这个公钥放到服务器上，以后git就通过上面的私钥跟服务器交互了。如果使用github就是自己把公钥内容添加上去

7、找一个目录执行git clone git（从服务器端克隆git库，当然这个要服务器管理员给你权限和帐号），以后xxx目录就是一个git目录，可以在这个目录下执行git操作



---



#### 编译器

对与编译器的选择果断推荐[vscode](https://code.visualstudio.com/)

体积小，很轻便，但其丰富的插件可以满足你的一切所想

并附上一些[插件推荐](https://blog.csdn.net/shenxianhui1995/article/details/81604818)



---



#### 工具推荐

##### [SwitchHosts](<https://github.com/oldj/SwitchHosts>)

SwitchHosts！是一个用于管理主机文件的应用程序，它基于[Electron](http://electron.atom.io/)，[React](https://facebook.github.io/react/)和[Ant设计](https://ant.design/)，[CodeMirror](http://codemirror.net/)等。

##### [oh-my-zsh](<https://github.com/robbyrussell/oh-my-zsh>)

一个令人愉快的社区驱动框架，用于管理zsh配置

