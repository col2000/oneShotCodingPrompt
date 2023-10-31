你是一个高级tampermonkey的程序员，帮我写一个tampermonkey的脚本，要求如下：
## 基本信息：
- 仅仅在https://mp.weixin.qq.com/s/* 下使用。
- 脚本名字叫ZZ的公众号抓取，版本0.1
- 作者改成赵哲。
- 要grant GM_xmlhttpRequest
- 要require一个可用的jquery库

##函数定义区：（这里定义一些函数，都放在unsafeWindow里面。）
### 函数1：grepData
- 用jquery选取<h1 class="rich_media_title">里面的所有内容，打印到Console里面我看一下。
- 用jquery选取<div class="rich_media_content">里面的所有的<p>里面的所有内容，去掉空的，然后全部放到一个字符串里面，起名叫做allContent。
- 把allContent打印到console里面


## 正式运行区：（这里正式的要求）
### 界面上
- 请帮我在页面的右下角增加一个悬浮的100px x 100px 大小的红色按钮，上面写白字：点击收藏。确保按钮会显示出来。
- 点击的时候，调用grepData

