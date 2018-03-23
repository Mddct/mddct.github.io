> hugo 静态博客系统，golang编写。
<!--more-->


## hugo

[hugo](https://gohugo.io)目录结构
```
.
├── archetypes
├── config.toml
├── content
├── data
├── layouts
├── public
├── static
└── themes
7 directories, 1 file
```
其中[theme](https://themes.gohugo.io)选择[even](https://themes.gohugo.io/hugo-theme-even/):
```bash
cp themes/even/exampleSiet/config.toml .
## 按照注释修改config.toml
## title = "Mddct - Blog" 
## defaultContentLanguage="zh-cn"
## author = "mddct"
## ...

```
```bash
## 写文章
hugo new post/{$articleName}.md
## 查看效果：
cd ~/hugo/; hugo server -D
```
<br>
主页效果：

![效果](/articleName.png "img")
主页会有刚刚建立的blog。具体使用方式参考[even](https://themes.gohugo.io/hugo-theme-even/)。

---

## github pages
### 建立仓库
[github pages](https://pages.github.com) 可以托管静态网页，可以用于项目展示等。将自己的blog托管到的github pages上。步骤：

- 建立新仓库 ${ProjectName}.github.io
- hugo -t ${yourhugotheme} 
- 此时会生成public，可以将public目录，push到刚刚创建的*.io的仓库

```
cd ~/hugo/public
git init 
git add .
git commit -m "blog test"

git remote add origin https://github.com/Your-Github-name/${ProjectName}.github.io.git
git push
```

几分钟后，访问链接[${ProjectName}.github.io](mddct.github.io)，就可以看见自己的主页。

### 绑定域名
- 获得自己的域名（购买 或 免费）
- github pages 中添加CNAME文件 

```
cd ~/hugo/public/; echo "www.mddct.club" >> CNAME
git add .
git commit -m "add CNAME"
git push
```
- 域名提供商里添加记录，参考 [github怎么绑定自己的域名？ - skycrown的回答 - 知乎](https://www.zhihu.com/question/31377141/answer/87541858)

![添加记录](/record.png "img")


---

## 自动化
TODO 编写blog 到 发布到github pages 实现自动化
