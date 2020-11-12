# git 安装与配置（windows版）

## 下载安装包

- 官网下载：https://git-scm.com/download/win

- 下载完.exe文件后，进行安装

## 安装步骤

- 安装步骤：

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029191631432.png" alt="image-20201029191631432" style="zoom: 80%;" />

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029191714095.png" alt="image-20201029191714095" style="zoom:80%;" />

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029191733819.png" alt="image-20201029191733819" style="zoom:80%;" />

接下来全都采用默认配置即可，一路下一步。。。

- 打开git-bash.exe，验证git是否成功

```shell
lizhe427@ZB-PF0ZN77V MINGW64 /
$ git --version
git version 2.29.1.windows.1
```

## 配置用户名和邮箱

- 新建一个目录 git_test，在 git_test 目录下创建一个版本库，命令如下：`git init`

```shell
lizhe427@ZB-PF0ZN77V MINGW64 /d/git_repositorys/git_test
$ git init
Initialized empty Git repository in D:/git_repositorys/git_test/.git/
```

- 指定用户名和邮箱

```shell
#设置用户名	
git config --global user.name 'lizhe427'
#设置邮箱
git config --global user.email 'lizhe427@jd.com'


##########################################
以下内容为扩展内容：

### 缺省等同于local
$ git config --local   # local只对某个仓库有效
$ git config --global  # global对当前用户所有仓库有效
$ git config --system  # system对系统所有登录的用户有效

### 显示config的配置，加--list
$ git config –-list --local
$ git config --list --global
$ git config –-list --system

### 问题：当同时设置了global范围的用户名、邮箱信息和local范围的用户名、邮箱信息时，会采用哪一个呢？
### 答：local的优先级要高于global。我统一使用 global 的范围。
git config –-local user.name ‘lizhe’
git config –-local user.email ‘1170063911@qq.com’
# 查看
git config –-local --list

# 上述设置得用户名和密码，实质上是对~/.gitconfig
lizhe427@ZB-PF0ZN77V MINGW64 /d/git_repositorys/git_test (master)
$ vim ~/.gitconfig
[user]
        name = lizhe427
        email = 1170063911@qq.com
[winUpdater]
        recentlySeenVersion = 2.29.1.windows.1
```

## 生成本机密钥

- 生成公钥、私钥

```shell
# 使用如下命令生成ssh密钥
$ ssh-keygen -t rsa -C ""
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/lizhe427/.ssh/id_rsa):
/c/Users/lizhe427/.ssh/id_rsa already exists.
Overwrite (y/n)? y
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/lizhe427/.ssh/id_rsa
Your public key has been saved in /c/Users/lizhe427/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:iMw3j3MAV7vweJyz9iV5emoiWi+3FKQ+YdJUHrjXsZk 1170063911@qq.com
The key's randomart image is:
+---[RSA 3072]----+
|       .+        |
|      .+ o.      |
|    . +.+. =     |
|   o *.O.oE      |
|    = @.S        |
|     = B + .     |
|      * * o o    |
|     .oBo..=.    |
|    .. +o++o     |
+----[SHA256]-----+
```

- 进入主目录下的~/.ssh文件件，下面有两个文件。

  ​	公钥为 id_rsa.pub

  ​	私钥为 id_rsa

  查看公钥内容，复制此内容。

```shell
$ cd ~/.ssh/
$ ll
total 13
-rw-r--r-- 1 lizhe427 1049089 2578 10月 29 21:47 id_rsa
-rw-r--r-- 1 lizhe427 1049089  554 10月 29 21:47 id_rsa.pub
-rw-r--r-- 1 lizhe427 1049089 4538  5月 28 22:43 known_hosts
$ cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDR+s+Zl4qq3zFED5YzgxiauXIIkK86hnxcPg0qUc9WXJuwLU/VDY7joCYx6waEmtoCkuezJsbsrcYEIMV1Rgx5HgTR/OjEpQrUq4YE6zB8ndvsX5CyUnxLvMzR5J80B1yvm87c7LMQERC0avNdrWqbSgqDtnAWqyAKoLmEfIf3v29J5d5QvV1dXNs54KjgoHSVbN80bN+usLQwy1MoH1KvWhPzc4PEoHBXwQzWSVwyUYUqASWbtj0O5iP2ctXG2j3dBk6kkvWxBn8oA+LET/6ckO/I4p97tVKtv2CDNo3HRWkxuTnz2L19eU2u+XfLjqAOwBQ9PmLQmPWN5e5YTF9SClWRgcpMsd3+TKquTfdHiBZ+P5QYYe1gbPzzhY1r9ojRv57xVdcJafqikyxJ5x2bXU5lDqMukG9i15YjYkE8q3RJ6VVZfg52hDXyvuELa5hXPfoxt/UQxE9QGL5lq8sPQJ8Sjy8llH3u1CRLMdUukncKHHZDOLj0H/+r7q4UevM=
```

## 创建 github 仓库

- 创建 github 仓库
- 注册 github 账户，登录后，点击"New respository "

![image-20201029215112786](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029215112786.png)

- 在新页面中，输入项目的名称，勾选'readme.md'，点击'create repository'

![image-20201029215700800](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029215700800.png)

- 添加成功后，转到文件列表页面。

![image-20201029215734133](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029215734133.png)

## 配置 github 关联本机公钥

- 在github添加ssh账户，以关联本地 git

![image-20201029215808984](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029215808984.png)

- 点击'SSH and GPG keys'，添加ssh公钥，复制本地git生成的id_rsa.pub中的公钥。

![image-20201029215523852](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029215523852.png)

## 本地拉取github项目

- 本地 git 拉取 github 项目 test。

![image-20201029220000354](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201029220000354.png)

```shell
$ git clone git@github.com:lzgkj1992/test.git
Cloning into 'test'...
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

