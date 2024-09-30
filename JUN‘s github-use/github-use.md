# git仓库使用

## 1.在本地新建一个空文件夹

## 2.上传文件

## 3. 在空文件夹内，右键选择Git Bash Here

![1](./github-use.assets/1.png)

## 4. 弹出GIT Bash框

## 5. 克隆远程仓库

**输入命令：**

```shell
git clone + 你的仓库地址
git clone  https://github.com/CQUJUN/JUN-Learning.git  //输入自己仓库
```

克隆成功，自动生成远程仓库文件

若克隆失败则

1. **取消代理设置**

   这是最常见的解决方法之一，通过在终端执行以下命令，可以取消 Git 的代理设置：

   ```shell
   git config --global --unset http.proxy 
   git config --global --unset https.proxy
   ```

## 6. 把需要上传的文件夹放入到远程仓库文件夹内

![2](./github-use.assets/2.png)

## 7. 上传

依次输入以下命令：

```shell
cd  JUN-Learning     //根据自己的远程仓库名输入
git init
git add .
git commit -m “你的提交信息”   //可以修改版本号即备注
git push
```

命令解释：

| 命令                         | 描述                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| cd + 你的远程仓库名          | 进入到远程仓库内（根据自己的仓库名输入）                     |
| git init                     | 初始话Git                                                    |
| git add .                    | 将工作区的文件添加到暂存区（“ . ”是当前目录下的所有文件，也可只输入文件夹名称） |
| git commit -m “你的提交信息” | 将暂存区的文件添加到本地仓库                                 |
| git push                     | 提交到远程仓库（可能需要你输入帐号和密码）                   |

# 为git bash设置代理

打开 `git bash`，然后输入

```stylus
git config --global http.proxy "http://127.0.0.1:1080"
git config --global https.proxy "https://127.0.0.1:1080"
```

端口号为自己设置，设置成不与电脑冲突的即可

这样设置之后，`git clone https://github.com/username/repo.git` 的速度基本能跑满带宽