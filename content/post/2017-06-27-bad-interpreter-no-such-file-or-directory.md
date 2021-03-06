---
title: "執行 sh 遇到的編碼問題"
date: "2017-06-27T14:21:00+08:00"
categories:
  - Bash
  - Windows
  - Vim
---

遇到的錯誤 message 如下：

```sh
env: node\r: No such file or directory
```

今天在 Linux 系統裡執行 .sh 時，遇到系統編碼格式不同所造成的問題  
問題原因是因為 Windows 的結尾字符和 Linux 系統不一樣（Windows 就是喜歡加料...

除了上面的 `env: node\r: No such file or directory` 之外，  
我還遇過 `/bin/sh^M: bad interpreter: No such file or directory`，

解決方法都一樣，使用 vim 開啟該檔案，使用以下命令查看文件格式，先確定是編碼問題

```
:set ff  
# 或是 
:set fileformat
```

如果看到`fileformat=dos`，那就是了，只要修改文件格式為`unix`，然後存檔覆蓋即可

```
:set ff=unix
:wq
```

