## Role 你是一个高级tampermonkey的程序员，帮我写一个tampermonkey的脚本，要求如下：

## 基本信息：
- 仅仅在https://mp.weixin.qq.com/s/* 下使用。
- 脚本名字叫ZZ的公众号抓取，版本0.1
- 作者改成赵哲。
- 要grant GM_xmlhttpRequest
- 要require一个可用的jquery库

## 函数定义区：（这里定义一些函数，都放在unsafeWindow里面。）

### 函数1：grepData
- 用jquery选取<h1 class="rich_media_title">里面的所有内容,去掉前后空格，命名为title，打印到Console里面我看一下。
- 用jquery选取<div class="rich_media_content">里面的所有<span>里的的inner text，按照顺序，去掉空的，然后全部放到一个字符串里面，起名叫做allContent。
- 把allContent打印到console里面
- 把当前页面的链接起名为link，并且打印到console里面
- 然后把title, linke, allContent作为参数，调用sendData

### 函数2：sendData
- 接收如下参数：<标题>，<链接>，<正文>
- 具体内容是使用GM_xmlhttpRequest来发送如下curl请求，请帮我翻译：
  curl -X POST "https://api.vika.cn/fusion/v1/datasheets/dstYxp24w5KhZH 
  ation: Bearer _你的token_" \
  -H "Content-Type: application/json" \
  --data '{
  "records": [
  {
    "fields": {
      "标题": "<标题>",
      "链接": "<链接>",
      "内容": "<正文>"
    }
  }
],
  "fieldKey": "name"
}'
- 帮我把返回值打印到console里面
- 然后帮我把<右下角按钮>的颜色变成绿色，文字改成刚刚返回值json里的message字段里的内容



###正式运行区：（这里正式的要求）
界面上
- 请帮我在页面的右下角增加一个悬浮的100px x 100px 大小的红色按钮，上面写白字：点击抓取。确保按钮会显示出来。这个按钮名字叫做<右下角按钮>
- 点击的时候，调用grepData