# actions-openwrt-helloworld

- **感谢** [P3TERX/Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)和[coolsnowwolf/lede](https://github.com/coolsnowwolf/lede)
- 通过创建流程文件，在线编译helloworld服务固件；
- 第一代passwall源码完全停止开发(开源源码已经移除)，基于vuejs脚本语言、焕新UI设计的第二代passwall由Lienol等大神们在私有库闭源开发中，看情况和心情，只有极小可能性以后某天开源，不要过分期待。  
- 修改流程文件`REPO_URL:` 不同库地址（默认lean的`https://github.com/coolsnowwolf/lede.git`或Lienol的`https://github.com/Lienol/openwrt`）；`REPO_BRANCH:` 不同分支 （以Lienol OpenWrt源码为例分支`dev-master` 激进；`dev-19.07` OpenWrt官方平稳版；`dev-lean-lede` lean的源码）。
- 通过修改`diy-part1.sh`文件修改`feeds.conf.default`配置。默认添加`fw876/helloworld`。  
  有能力可以添加包含`passwall`的`lienol-openwrt-package`试试。
- 通过修改`diy-part2.sh`文件可以自定义默认IP，登陆密码等。按我的需要现在的默认IP为192.168.1.11
- 修改流程触发条件。默认添加两种触发方式：  
**“`Webhook`”**（给 GitHub API 发送一个 `repository dispatch event`(仓库调度事件) 请求，当 API 接收到请求后就会触发相应的 `workflow`）  
以下是一个使用 `cURL` 发送请求的例子：  
`curl -X POST https://api.github.com/repos/:owner/:repo/dispatches \`  
`     -H "Accept: application/vnd.github.everest-preview+json" \`  
`     -H "Authorization: token ACTIONS_TRIGGER_TOKEN" \`  
`     --data '{"event_type": "TRIGGER_KEYWORDS"}'`  
需要要替换的值：  
`:owner`- 用户名  
`:repo` - 需要触发的 Github Action 所在的仓库名称  
`ACTIONS_TRIGGER_TOKEN` - 带有 repo 权限的 Personal access token  
`TRIGGER_KEYWORDS` - 自定义 `Webhook` 事件名称，可以为任意值，Actions 列表中会显示此名称。  
**“`Star`”**（点击仓库上的 `Star` 按钮即可触发 `GitHub Actions`的工作流程，为了避免被其他人点击 `Star` 导致的不必要的麻烦，只有仓库所有者，也就是你自己点 `Star` 才有效）。
- 在触发工作流程后，默认`SSH_ACTIONS: true`在 Actions 页面等待执行到`SSH connection to Actions`步骤，会出现下面信息：  
  ***
  `To connect to this session copy-n-paste the following into a terminal or browser:` 
  
  `ssh Y26QeagDtsPXp2mT6me5cnMRd@nyc1.tmate.io`    
  
  `https://tmate.io/t/Y26QeagDtsPXp2mT6me5cnMRd`     
  ***
- 复制 SSH 连接命令粘贴到终端内执行，或者复制链接在浏览器中打开使用网页终端，登陆云menuconfig。
- 命令：`cd openwrt && make menuconfig`
- 新手参考[OpenWrt MenuConfig设置和LuCI插件选项说明](https://mtom.ml/827.html)   
- 完成后按快捷键`Ctrl+D`或执行`exit`命令退出，后续编译工作将自动进行。
- 这样比较灵活，可以根据路由器硬件通过云`menuconfig`自定义配置固件，不需要再导出`.config`和上传
- 进阶玩法请看P3TERX的博客[中文教程](https://p3terx.com/archives/build-openwrt-with-github-actions.html)
### 使用同步`.config`多流程编译移步[Actions-Lean-OpenWrt](https://github.com/Lancenas/Actions-Lean-OpenWrt)
