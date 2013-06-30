---
layout: post
title: "如何在 Octopress 中建立 about 頁面"
date: 2013-06-30 13:34
comments: true
categories: Octopress
---
當在逛別人用 Octopress 建立的[網站](https://github.com/imathis/octopress/wiki/Octopress-Sites)時，
看到一些非 blog 的頁面，如 About，這是官網安裝步驟沒有提到的。經過尋找後，看到好心人士簡單說明他的作法。
要建立 About 頁面只需要兩個動作：

1. 用 rake 產生一個名為 about 的 page : `rake new_page["about"]`
2. 將此 page 的聯結放到 menu 上 : 修改 template `./source/about/index.markdown`

詳細步驟請見 [Add about page to Octopress](http://amaras-tech.co.uk/article/222)。
