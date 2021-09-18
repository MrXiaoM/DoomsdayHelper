# 发表文章

如果你已熟知如何使用 `Github` 的 `Pull Requests`，代表你不需要查看此教程，[请火速去写然后PR上来](https://github.com/DoomsdaySociety/DoomsdayHelper/pulls)，记得改 `list.json`

**如果你无法访问 `Github`，可以尝试连接代理服务器或者使用如 [fastgit](https://hub.fastgit.org/) 之类的镜像站**

## 注册账号

要在本网站发表文章，你需要拥有一个 `Github 账户`，[点击此处可以去注册](https://github.com/signup)，按照提示操作即可。如果你已经注册过，可以跳过此步。

## 拷贝仓库

要发表文章，首先你要将储存文章的仓库拷贝到你的账户

进入 [DoomsdaySociety/DoomsdayHelper](https://github.com/DoomsdaySociety/DoomsdayHelper) 点击右上角的 Fork

然后你就能在你的仓库列表看到 DoomsdayHelper 了

## 编写文章

在你的仓库拷贝中，进入 `posts` 文件夹，点击 `Add file`，选择创建文件 (`Create new file`) 然后开始编写吧！

文章中支持使用 Markdown 语法，如果你需要语法相关帮助[请点这里](https://www.runoob.com/markdown/md-tutorial.html)

以下是常用的语法，**请注意，Markdown 语法中两个换行或者两个空格为换一行！**

````markdown
# 大标题
## 二级标题
### 三级标题
**加粗**
*斜体*
***粗体+斜体***
> 引用内容
```
代码段
```
`代码`
![图片](图片地址)
[链接文字](链接地址)
````

## 发表文章

在检查你的文章没有错漏之后，就可以开始发表了。你可以一次写多篇文章一起发布。

[点此前往 Pull Requests](https://github.com/DoomsdaySociety/DoomsdayHelper/pulls)，点击 `New pull request`，点击 `compare across forks`，并在下方的 `head respository` 选中你拷贝的仓库，此时 `Create pull request` 按钮会亮起，点它，就会让你填一些信息，如 `Title` 和 `Leave a comment`，你可以在里面简要概述下文章内容什么的，也可以什么都不填。

都准备好后，再点击 `Create pull request` 即可申请发表文章，在经管理组的质量检查通过后将会将你的 PR 合并到仓库中，之后，你就能在本网站看到你的文章了。

## list.json

这个文件是网站首页的所有文章列表，在仓库根目录，如果你不会填的话，可以直接跳过，在合并 PR 到仓库时管理组会帮你填，当然要是你能填那是再好不过了，按照格式复制粘贴然后修改就是了。

```json
    {
		"title": "标题",
		"author": "文章作者",
		"color": "#十六进制的标题颜色",
		"bold": "布尔值，标题是否加粗",
		"time": "创建日期，年-月-日",
		"file": "posts/对应文件名.md"
	}
```

**务必保持“服务器规则”和“更新日志”在最下面，以保证这两篇文章能够置顶**

不要滥用颜色，否则管理组会将颜色设置回 #000