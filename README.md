# actions-openwrt-passwall

- 感谢P3TERX/Actions-OpenWrt和Lienol/openwrt
- 通过修改流程文件，使用Lienol's openwrt在线编译passwall服务固件
- 使用P3TERX/Actions-OpenWrt进阶玩法中的云menuconfig，直接 SSH 或 浏览器 到 Actions 进行操作（具体看[Actions OpenWrt PassWall|教程](https://mtom.ml/798.html)）
- 在触发工作流程后，在 Actions 页面等待执行到SSH connection to Actions步骤，会出现下面的信息。
- To connect to this session copy-n-paste the following into a terminal or browser:
- [ssh Y26QeagDtsPXp2mT6me5cnMRd@nyc1.tmate.io]
- [https://tmate.io/t/Y26QeagDtsPXp2mT6me5cnMRd]
- 复制 SSH 连接命令粘贴到终端内执行，或者复制链接在浏览器中打开使用网页终端。
- cd openwrt && make menuconfig
- 完成后按快捷键Ctrl+D或执行exit命令退出，后续编译工作将自动进行。
- 这样比较灵活，可以根据路由器硬件通过云menuconfig自定义配置固件，不需要再导出.config和上传
- 进阶玩法请看P3TERX的[Read the details in my blog (in Chinese) | 中文教程](https://p3terx.com/archives/build-openwrt-with-github-actions.html)
