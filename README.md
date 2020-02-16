# 感谢P3TERX/Actions-OpenWrt和Lienol/openwrt
- 通过修改流程文件，使用Lienold openwrt在线编译passwall服务固件
- 使用P3TERX/Actions-OpenWrt进阶玩法中的云menuconfig，直接 SSH 或 浏览器 到 Actions 进行操作（具体看[Read the details in my blog (in Chinese) | 中文教程](https://p3terx.com/archives/build-openwrt-with-github-actions.html)）
- 在触发工作流程后，在 Actions 页面等待执行到SSH connection to Actions步骤，会出现下面的信息。
To connect to this session copy-n-paste the following into a terminal or browser:
ssh Y26QeagDtsPXp2mT6me5cnMRd@nyc1.tmate.io
https://tmate.io/t/Y26QeagDtsPXp2mT6me5cnMRd
- 复制 SSH 连接命令粘贴到终端内执行，或者复制链接在浏览器中打开使用网页终端。
- cd openwrt && make menuconfig
- 完成后按快捷键Ctrl+D或执行exit命令退出，后续编译工作将自动进行。
- 这样可以比较灵活，可以自己通过云menuconfig配置路由固件，不需要再导出.config和上传

# Actions-OpenWrt

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/P3TERX/Actions-OpenWrt/blob/master/LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/P3TERX/Actions-OpenWrt.svg?style=flat-square&label=Stars&logo=github)](https://github.com/P3TERX/Actions-OpenWrt/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/P3TERX/Actions-OpenWrt.svg?style=flat-square&label=Forks&logo=github)](https://github.com/P3TERX/Actions-OpenWrt/fork)

Build OpenWrt using GitHub Actions

[Read the details in my blog (in Chinese) | 中文教程](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

## Usage

- Click the [Use this template](https://github.com/P3TERX/Actions-OpenWrt/generate) button to create a new repository.
- Generate `.config` files using [Lean's OpenWrt](https://github.com/coolsnowwolf/lede) source code. ( You can change it through environment variables in the workflow file. )
- Push `.config` file to the GitHub repository, and the build starts automatically.Progress can be viewed on the Actions page.
- When the build is complete, click the `Artifacts` button in the upper right corner of the Actions page to download the binaries.

## Acknowledgments

- [Microsoft](https://www.microsoft.com)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub](https://github.com)
- [GitHub Actions](https://github.com/features/actions)
- [tmate](https://github.com/tmate-io/tmate)
- [mxschmitt/action-tmate](https://github.com/mxschmitt/action-tmate)
- [csexton/debugger-action](https://github.com/csexton/debugger-action)
- [Cisco](https://www.cisco.com/)
- [OpenWrt](https://github.com/openwrt/openwrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)

## License

[MIT](https://github.com/P3TERX/Actions-OpenWrt/blob/master/LICENSE) © P3TERX
