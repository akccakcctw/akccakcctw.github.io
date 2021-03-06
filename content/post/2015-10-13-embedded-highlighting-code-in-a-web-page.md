---
date: "2015-10-13T16:05:00+08:00"
title: "在網頁中嵌入高亮程式碼"
---

有時候，我們需要在頁面中分享程式碼，但可能會發現：

- 它居然被執行了！
- 沒有 highlight 眼睛很痛……
- 有 highlight，但是配色不好看

嵌入的方法有很多，以下利用 google 的 [code-prettify](https://github.com/google/code-prettify)，此方法適用__支援 Javascript__ 的部落格，或者是自己架設的個人網站。

---

1. 把你想要貼的 code 重新編碼（encode），以免被瀏覽器執行了。
推薦使用[此工具](http://www.opinionatedgeek.com/DotNet/Tools/HTMLEncode/Encode.aspx)。

2. 在`body`最後引用這個 JS 檔。
```html
<script src="https://cdn.rawgit.com/google/code-prettify/master/loader/run_prettify.js"></script>
```
這是 Google 提供的服務，除了最常見的`HTML`、`XML`、`CSS`、`Javascript`之外，幾乎主流的語法都有支援（
[點此看效果](https://rawgit.com/google/code-prettify/master/examples/quine.html)），有興趣的朋友也可以至 [Google Code Prettify](https://github.com/google/code-prettify) 深入了解。
如果你會修改部落格的 CSS，[這裡還有提供幾種主題](https://cdn.rawgit.com/google/code-prettify/master/styles/index.html)，可以直接套用，像我就滿喜歡 sunburst 的。

3. 將你重新編碼過的程式碼，用以下方式包住。
```html
<pre class="prettyprint">
        你的程式碼
</pre>
```

4. 大功告成！
