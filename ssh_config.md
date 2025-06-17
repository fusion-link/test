# MAC 电脑拉取远端 GitHub 仓库到本地

## 安装 Brew

> 参考文档 https://www.igeeksblog.com/how-to-install-homebrew-on-mac/

1. 登录 https://brew.sh/ 安装 Homebrew。
2. 将 Homebrew 添加到 PATH。

   ```
   cd /opt/homebrew/bin/
   ls
   PATH=$PATH:/opt/homebrew/bin
   cd
   touch .zshrc
   echo 'export PATH=$PATH:/opt/homebrew/bin' >> .zshrc
   brew doctor
   ```

3. 输入 `brew --version` 命令查看版本。

## 安装 Git

登录 https://git-scm.com/ 下载对应的 Git 并安装。

## 安装 SourceTree 并配置 SSH

> 参考文档 https://www.jianshu.com/p/ac392489f9c1

1. 下载并安装 SourceTree https://www.sourcetreeapp.com/。
2. 配置 SSH。
   1. 打开终端输入命令 `cd ~/.ssh` 查看是够已经存在 .ssh 文件，若不存在则使用 `touch ~/.ssh` 命令创建。
   2. 输入 `nano ~/.ssh/config` 命令创建并编辑 config 文件。
   3. 将下述内容复制到 congif 文件中，并保存。
      ```
      Host github.com
      Hostname ssh.github.com
      Port 443
      User git
      ```
   4. 输入 `ssh-keygen -t rsa -C "youremail@example.com"`，会在 .ssh 目录下生成 id_rsa、id_rsa.pub 两个私钥和公钥. 后面连续输入三次回车即可。
   5. 输入命令 `cat ~/.ssh/id_rsa.pub` 查看获取到的公钥，复制这个公钥地址，添加到 GitHub 的 SSH 配置中。
   6. 输入 `ssh git@github.com` 命令查看是否链接成功。

## 使用 SourceTree

输入 URL 即可。
