# picgo和github图床的使用

## 参考资料：

https://www.jianshu.com/p/e138e5546d83

## markdown 关联 github 图床 步骤：

### Github 创建图床：

- 新建一个 repository，名字随便填，记得选 public，否则外链不能访问。

![image-20201012200532183](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012200532183.png)

- 生成 token 以便 PicGo 访问，Select scopes 时，勾选红框中的就好了，然后点击生成。记得马上将其复制下来，否则等你再次打开s就看不到了。

![image-20201012200713461](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012200713461.png)

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012200750406.png" alt="image-20201012200750406" style="zoom:67%;" />

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012200840034.png" alt="image-20201012200840034" style="zoom:67%;" />

![image-20201012200908535](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012200908535.png)

- 注意：token生成后，要第一时间记住、保存，因为只能看一次

### token

```shell
9cfbeef5359ec9162c918e5f63a3cb9c672270d1
```

### 下载PicGo：

PicGo下载地址：https://github.com/Molunerfinn/PicGo/releases

- 注意：2.3.0版本不稳定，在使用过程中可能出现未知问题

![image-20201012194930858](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012194930858.png)

- 建议选择一个稳定的版本

![image-20201012194958709](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012194958709.png)

![image-20201012195023765](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012195023765.png)

### 安装PicGo：

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012195429347.png" alt="image-20201012195429347" style="zoom: 67%;" />

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012195527455.png" alt="image-20201012195527455" style="zoom:67%;" />

### 配置 PicGo：

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012195634847.png" alt="image-20201012195634847" style="zoom: 50%;" />

### 配置 markdown

文件 -> 偏好设置 -> 图像

<img src="https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012201149996.png" alt="image-20201012201149996" style="zoom:67%;" />

## 可能遇到的错误：

![image-20201012201245784](https://raw.githubusercontent.com/lzgkj1992/markdown_images/master/image-20201012201245784.png)

**解决方法：**

- 根据错误提示：到 C:\Users\lizhe427\AppData\Roaming\picgo\，将内容清空

- 重装一遍

## 创建第二个图床

![image-20201021124842716](https://i.loli.net/2020/10/21/MsxTH13E9UmFGh6.png)

token

```
907d979600f20f021f39bf495bd0384f56a7b839
```