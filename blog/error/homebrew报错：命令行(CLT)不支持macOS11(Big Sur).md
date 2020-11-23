# Homebrew: Your CLT does not support macOS 11.0

## 我想要做什么？

我想要使用homebrew安装yarn

## 发生了什么？

安装失败了

```
You are using macOS 11.0.
We do not provide support for this released but not yet supported version.
You will encounter build failures with some formulae.
Please create pull requests instead of asking for help on Homebrew's GitHub,
Twitter or any other official channels. You are responsible for resolving
any issues you experience while you are running this
released but not yet supported version.

Your CLT does not support macOS 11.0.
It is either outdated or was modified.
Please update your CLT or delete it if no updates are available.
```

## 解决方法

把以前的命令行工具删了，下载个新的就行

```bash
sudo rm -rf /Library/Developer/CommandLineTools
sudo xcode-select --install
```



## 后记

使用命令`brew doctor`的时候终端返回了这个信息给我

```bash
Warning: A newer Command Line Tools release is available.
Update them from Software Update in System Preferences or run:
  softwareupdate --all --install --force

If that doesn't show you an update run:
  sudo rm -rf /Library/Developer/CommandLineTools
  sudo xcode-select --install

Alternatively, manually download them from:
  https://developer.apple.com/download/more/.
```

有一说一其实这个地方已经告诉我了怎么解决这个问题，但是我一开始没看到，因为后面还有很多东西，我就没往上翻。以后多注意。



