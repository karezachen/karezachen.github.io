---
layout: post
title: 优雅的命令行
date: 2021-03-01 14:17
categories: [命令行, prompt]
---

# 优雅的命令行

## 预览图

![优雅的命令行_预览图](../../illustration/优雅的命令行_预览图.png)

- 详细的命令行信息
- 高效的Git反馈
- 命令提示（一键补全）
- 语法高亮提醒
- 更多插件或主题可自行配置

## 前情提要

前几天在我的微信公众号中更新了一篇关于命令行的文章[《左手咖啡，右手命令行》](https://mp.weixin.qq.com/s/tXemDoVNEBtMGvvNqphGEQ)，讲了讲走开发这几年我用命令行的经历，对命令行的优雅之处还不甚了解的同学可以去看一看。

本文是对那篇文章的补充，因为空口无凭，我越强调命令行可能有些读者会越加觉得言过其实，所以这篇定位为教程类的文章，可以带领你完成命令行的配置，让你的命令行也完成华丽变身。

## 强大的zsh

在命令行起飞之前，先要选对命令行工具，传统的bash、sh工具显然不具备太强的扩展能力，也缺乏一个活跃的社区支持插件的升级。

而zsh却能够担此重任。

它的扩展项目oh-my-zsh至今在GitHub上已经收获了122k的星，拥有超过1700人为项目贡献过，近300个可选组件……

在ubuntu 20.10上只需要两行命令即可安装zsh并将其设置为默认命令行工具。
*作者偏执的认为如果不使用和作者相同的环境，那你应该具备“翻译”作者提供的命令的能力*

```shell
apt update
apt install zsh
```

## 优雅的oh-my-zsh

zsh当然是易于扩展的，但这需要比较高的开发素养，而且即使你开发了一个十分棒的组件，你可能一分钱也得不到（虽然你可能可以从中获取到极大的乐趣）。所以对于绝大多数人而言，使用那些优秀程序员开发并开源出来的组件，无疑是很正确的选择。

这里就要提到上文的oh-my-zsh项目，上文我们已经介绍过这个项目的受欢迎程度，这边就不再赘述。

想要安装oh-my-zsh，你需要先在你的机器上安装git工具。

假设你还未安装git工具，你可以通过以下两行命令安装。

```shell
apt update
apt install git
```

在这之后，你可以使用作者的开源项目[mydev](https://github.com/karezachen/mydev.git)完成后续的oh-my-zsh安装，以及配置和作者一样的命令行。（图见文章开头）

以下两行命令可以安装oh-my-zsh
**(安装脚本复制自官方，因为官方提供的下载地址经常会出现被墙的情况，故复制到自己的项目中)**

```shell
git clone https://github.com/karezachen/mydev.git
sh -c mydev/oh-my-zsh/install.sh
```

以下一行命令可安装命令提示（一键补全）插件（未在zsh配置中开启，所以暂时不生效）

```shell
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

以下一行命令可安装语法高亮插件（未在zsh配置中开启，所以暂时不生效）

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

将作者的zsh配置文件移到覆盖安装时默认的zsh配置文件,并使配置生效

```shell
cp mydev/oh-my-zsh/.zshrc ~/.zshrc
source ~/.zshrc
```

如果你完整的阅读了作者的这篇文章，并顺利的跟着操作了一遍。

你现在应该已经拥有了一个在咖啡馆会被搭讪的命令行工具！

这就收拾好包出发吧～🍀

