---
layout: post
title: "Bitmessage"
date: 2013-06-15 22:21
comments: true
categories: [Bitmessage]
---
你在用 email 時，可會擔心自己放在伺服器上的資料被人窺看？如果說 email 服務商或是政府可以
任意查看你的郵件內容時，你有什麼想法？
[Bitmessage](https://bitmessage.org/wiki/Main_Page) 是一種 P2P 的通訊協定，可以讓你安全的發訊息給另外一個人，
或是任意數量的訂閱者，而不用擔心訊息內容被其他人窺探。

使用 Bitmessage
---
Windows 安裝程式由此[下載](https://bitmessage.org/download/windows/Bitmessage.exe)。使用 Mac 的朋友請見下一段
我的安裝經驗。開啓程式後是空白狀態，你需要先建立自己的地址，點選 "Your Identities" 分頁。

{% img https://lh5.googleusercontent.com/-iV5f4QcTBWg/Ubx85n7C9QI/AAAAAAAAAlw/7Et8D9GCKmk/s938/bitmessage-identity.png %}

有兩種產生地址的方式，先採用預設值即可。產生地址後就可以選 "Send" 分頁來寄出訊息給朋友。
趕快讓你的朋友也裝上 Bitmessage 吧。

寄出訊息有兩種方法:

1. Send to one or more specific people
2. Broadcast to everyone who is subscribed to your address

第一種就像一般的 email ，指定收件者的地址。第二種比較有意思，可以讓別人來訂閱你的地址，當你選擇這個方式時，
所有訂閱你地址的人都會收到信。

群組寄信
---
想像 A、B、C 三人要一起討論，一個方法是每個人都寄信給另外兩個人，
這種方法可以運作，但是將來有其他人要加入時，每個人都要增加自己的清單。
比較好的方法是利用群組信。

Bitmessage 有一個很棒的功能，可以達成群組信的功能。
設定方法為，打開 "Your Identiies" 分頁，右鍵點選某個地址，
然後選 "Special address behavior"，接著把行為設定成 "Behave as a pseudo-mailing-list address"。
接下來每個想收到討論訊息的人，都訂閱此地址，想發訊息給群組的人，就直接寄信到這個地址。

到此還有一個小問題，那就是建立群組地址的人必須持續執行 PyBitmessage。
建議利用 Linux 伺服器來執行一個沒有 UI 的 daemon。方法請見[這裡](https://bitmessage.org/wiki/Daemon)。

安裝在 Max OS X 10.8 上
---
到 2013 年 6 月為止，目前的 Bitmessage 版本為 0.3.3-2 Beta，只有提供 Windows 版的執行檔。
Linux 和 Mac 的朋友需要由源碼安裝。
雖然官方網站提供了由源碼安裝的[方法](https://bitmessage.org/wiki/Compiling_instructions)，
但是實際執行時會遇到一些困難，以下是我自己嘗試在 Max OS X 10.8 上的安裝經驗。

### 安裝 Homebrew 套件管理程式

    ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"

### 若Mac內建的 Python 的版本早於 2.7.3 ，用 brew 安裝新版的 Python 2.7.5

    brew install python
    brew link --overwrite python
    sudo mv /usr/bin/python /usr/bin/python.original
    sudo ln -s /usr/local/Cellar/python/2.7.5/bin/python /usr/bin/python

### 安裝 openssl

    brew install openssl

### 安裝 pyqt

    brew install pyqt

如果你在安裝 pyqt 時遇到錯誤

    ImportError: No module named sipconfig

那表示你還需要安裝 SIP ，請到[此處](http://www.riverbankcomputing.co.uk/software/sip/download)下載。
解壓縮檔案後到目錄下使用以下指令安裝：

    python configure.py
    make
    sudo make install

現在繼續執行 `brew install pyqt` 就沒問題了。請注意安裝 pyqt 很花時間，請耐心等候。

### 下載 PyBitmessage 並執行

    cd ~/
    git clone git://github.com/Bitmessage/PyBitmessage.git
    cd PyBitmessage
    python src/bitmessagemain.py

如果你不巧跟我一樣遇到以下錯誤:

    Problem: The version of SQLite you have cannot store Null values.
    Please download and install the latest revision of your version of Python
    (for example, the latest Python 2.7 revision) and try again.
    PyBitmessage will now exit very abruptly.
    You may now see threading errors related to this abrupt exit
    but the problem you need to solve is related to SQLite.

請執行步驟2，升級 Mountain Lion 預設的 Python 到 2.7.5 或以上。

參考資料
---
* [中文化以及簡介](http://btm.wmqying.com/)
