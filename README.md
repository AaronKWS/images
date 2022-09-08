# images
一个一劳永逸的图床

---

经常用markdown记笔记或者写博客的朋友应该会遇到和我类似的问题，那就是文章中的图片需要有一个长久稳定的地方存放，最早之前使用的是一个免费的图床sumiao，但是还没到一年就挂了，里面的图片全部作废，然后我就像搭建一个自己的图床，买了服务器，然后将一个很有名的图床[Lsky Pro](https://www.lsky.pro/)发布上去，嗯！帧不搓，可惜只有500M的空间，最重要的是服务器好贵，到期了没钱续费，就又白忙活了，所以意外在网线发现了[PicGo](https://github.com/Molunerfinn/PicGo)，而且最重要的是支持很多图床，如下所示：

- `七牛图床`
- `腾讯云 COS v4\v5 版本`
- `又拍云`
- `GitHub`
- `SM.MS V2`
- `阿里云 OSS`
- `Imgur`

# 具体步骤

## 下载安装（详细请参阅[官网](https://github.com/Molunerfinn/PicGo)）

| 下载源  | 地址/安装方式  | 平台 | 备注  |
|---|---|---|---|
| GitHub Release  | https://github.com/Molunerfinn/PicGo/releases | All | 国内下载速度可能会慢 |
| [腾讯云COS](https://cloud.tencent.com/product/cos)  | https://github.com/Molunerfinn/PicGo/releases 附在更新日志结尾 | All | 感谢 [腾讯云COS](https://cloud.tencent.com/product/cos) 提供的赞助支持 |
| [山东大学镜像站](https://mirrors.sdu.edu.cn/) | https://mirrors.sdu.edu.cn/github-release/Molunerfinn_PicGo | All | 感谢 [山东大学镜像站](https://mirrors.sdu.edu.cn/) 提供的镜像支持 |
| [Scoop](https://scoop.sh/) | `scoop bucket add helbing https://github.com/helbing/scoop-bucket` & `scoop install picgo` | Windows | 感谢 @helbing 的贡献 |
| [Chocolatey](https://chocolatey.org/) | `choco install picgo` | Windows | 感谢 @iYato 的贡献 |
| [Homebrew](https://brew.sh/) | `brew install picgo --cask` | macOS | 感谢 @womeimingzi11 的贡献 |
| [AUR](https://aur.archlinux.org/packages/yay) | `yay -S picgo-appimage` | Arch-Linux | 感谢 @houbaron 的贡献 |

因为我使用的是macOS，所以为了省事直接使用brew安装，安装后就会出现到应用程序中打开即可

## 新建仓库
![](https://segmentfault.com/img/remote/1460000041076408)
仓库必须要设置为公有仓库，不然图片无法展示，这其实算是唯一的缺点，就是公有的话别人访问你的github仓库，就能看到你上传的全部图片，但是我需要上传的图片基本都是网上或者截图，所以不是很重要。
仓库建好之后，点击页面右上角，进入 Settings：
![](https://segmentfault.com/img/remote/1460000041076409)
然后进入 Developer settings：
![](https://segmentfault.com/img/remote/1460000041076410)
点击 Personal access tokens，再点 Generate new token 新建 token。
![](https://segmentfault.com/img/remote/1460000041076411)
填写 Notes 信息，选择 token 过期时间，为了安全，GitHub 会强烈建议不要设置成永久。这个大家根据自己实际情况选择，到期之后重新生成即可。

复选框的话，repo 一定要全选，其他的无所谓，我是都勾选了。

确定之后，就生成我们需要的 token 了。
https://segmentfault.com/img/remote/1460000041076412

## 配置 PicGo
![](https://segmentfault.com/img/remote/1460000041076413)
- 设定仓库名：上文在 GitHub 创建的仓库。
- 设定分支名：main。
- 设定 Token：上文生成的 token。
- 指定存储路径：为空的话会上传到跟目录，也可以指定路径。
- 设定自定义域名：可以为空，这里为了使用 CDN 加快图片的访问速度，按这样格式填写：https://cdn.jsdelivr.net/gh/用户名/仓库名

## 配置完成
到这里就可以使用了

流程参自：
https://segmentfault.com/a/1190000041076406
https://github.com/Molunerfinn/PicGo/blob/dev/README.md
