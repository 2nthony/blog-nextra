---
title: 我的 Shell 配置
date: 2021-10-24
tag: Shell,Vim,Coding
description: 在 Shell 上编码无比帅气
---

![](https://evilaassets.oss-cn-shanghai.aliyuncs.com/uPic/2022/02/emDzO3.png)

## macOS

你可以跟着我的 [dotfiles 仓库](https://github.com/2nthony/dotfiles)，配合原作者的视频步骤来实现。过程很枯燥并且我认为有些难度，但到最终完成的时候，绝对会有成就感。

我之前就有将 VIM 打造成 Web IDE ： [打造 VIM 成为 Web IDE](https://www.notion.so/VIM-Web-IDE-f165a0ea5fe84c83a00192b6ee72b0b5) ，因为依靠于 coc.nvim ，所以在智能提示上非常接近 VSCode ，并且生态非常丰富。

不过由于我什么都喜欢 ”原生“ 的原因，我偶尔都会使用关键词 `use vim as web ide` 在 Google 上搜索，期待有新惊喜。

果不其然，我找到了[这篇文章](https://dev.to/craftzdog/my-vim-setup-to-speed-up-javascript-coding-for-my-electron-and-react-native-apps-4ebp)，这篇文章同样还是使用 coc.nvim ，不过吸引我的是这个高颜值的 Shell 。

这才是我理想中 **Geeker** ，**我决定必须要把自己的 shell 搞成这个样子**，于是顺着 Youtube 频道找到了他公开的 dotfiles 仓库（可以在本文顶部的仓库 README 处找到）并在此基础上做一些改动，例如我需要添加 Vue ， Svelte 和 Go 相关的 lsp 。让我惊喜的是，作者已经从 coc.nvim 切换到了 neonvim 内置的 lsp 系统中，这让我更兴奋了。

但是这整一个过程并不是无障碍的，此时此刻（10 月 24 日）原作者的仓库最后更新日期只间隔了一个月，已经有一些插件没有跟上 nvim(—HEAD) 的更新而不能用了。

> 通过 `:message` 查看错误信息，在 Google 上搜索，找到一系列 stackoverflow 和 GitHub issues ，查看解决办法。  
> 这个过程也不太容易，毕竟 Google 上搜到的答案也不是最理想的答案，总会有一些相似但不相关结果的排在最前。  
> 例如 lspsaga 插件，我发现在我的环境中 `shift + k` 查看代码定义出现错误，根据错误信息 Google 无果；同样的 `\ca` 代码填充操作也出现错误，但是这个错误信息在 Google 搜索的解决方案中**同时**解决了这两个问题。

但最终的结果是好的，除了还未熟悉按键和未知的问题。

🤥

## Windows WSL(Ubuntu)

> 我相信 Windows 将来会 built-in WSL ，因此我不打算处理 Windows 环境。好在是原作者最近提供了 Windows 环境配置给弄上了。

不过由于有需要，我也在 Windows 上弄了一番，记录一下下面的情况。

在使用 git 的过程中可能会出现 `fatal: could not set 'core.filemode' to 'false'`

编辑 `/etc/wsl.conf` 添加如下内容：

```jsx
;[automount]
options = 'metadata'
```

`exit` 并在 PowerShell 运行 `wsl --shutdown` 再重新进入 WSL 即可。

如果出现 `C compiler` 相关则安装：

```jsx
sudo apt install build-essential
```
