---
layout: post
title: "octopress"
date: 2013-06-07 17:32
comments: true
categories: [Octopress]
---
新 blog 的第一篇文就決定獻給 Octopress 這套 Blog framework。
這篇文章主要是想推薦 Octopress，只要你會用 Git ，使用上大概就沒有問題。
像我對 Octopress 使用的 Jekyll 和 Ruby 都不熟，
但是只要依照[官方說明](http://octopress.org/docs/setup/)，
不用一小時就能在 [Github Pages](http://pages.github.com/) 上建立一個自己的 blog。

Octopress 有多好用？我只能說對 Programmer 實在親切，如以下幾點：

* 動靜分離。Octopress 利用 Jekyll 產生單純的 html ，不需要在 server 上裝 PHP, mysql 等一堆服務。單純的 HTTP server 就好了。寫好 blog 可以在自己的電腦上下 `rake preview` 指令，就可以在本機的 4000 埠上預覽。
* 可以用 Vim 寫 [Markdown](http://markdown.tw/)，實在是比之前在 blogspot 方便太多了。Markdown 的例子如下：

{% codeblock %}
    新 blog 的第一篇文就決定獻給 Octopress 這套 Blog framework。
    ...
    * 動靜分離。Octopress 利用 Jekyll 產生單純的 html ...
    * 可以用 Vim 寫 [Markdown](http://markdown.tw/)，實在是比之前在 blogspot 方便太多了。...
{% endcodeblock %}

* 可以用 Git 作版本控制，文章可以在自己的電腦上修修改改，預覽之後再上傳
* 使用 Github 同時兼有備份功能，再也不用煩惱備份
* 貼程式碼時，有內建 [Solarized](http://ethanschoonover.com/solarized) 配色，和我在 Vim 中用的一樣，看起來相當順眼

其餘好處請見 XDite 大大的 [Why Octopress?](http://blog.xdite.net/posts/2011/10/07/what-is-octopress/)
