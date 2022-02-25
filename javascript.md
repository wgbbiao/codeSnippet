页面滚动

```javascript
element.scrollIntoView(); // 等同于element.scrollIntoView(true)
element.scrollIntoView(alignToTop); //布尔参数
element.scrollIntoView(scrollIntoViewOptions); //对象参数
```

alignToTop	[可选]，目前之前这个参数得到了良好的支持
true	元素的顶部将对齐到可滚动祖先的可见区域的顶部。对应于scrollIntoViewOptions: {block: "start", inline: "nearest"}。这是默认值
false	元素的底部将与可滚动祖先的可见区域的底部对齐。对应于scrollIntoViewOptions: {block: "end", inline: "nearest"}。
scrollIntoViewOptions	[可选]，目前这个参数浏览器对它的支持并不好，可以查看下文兼容性详情
behavior	[可选]定义过渡动画。"auto","instant"或"smooth"。默认为"auto"。
block	[可选] "start"，"center"，"end"或"nearest"。默认为"center"。
inline	[可选] "start"，"center"，"end"或"nearest"。默认为"nearest"。

示例

```javascript
var element = document.getElementById("box");

element.scrollIntoView();
element.scrollIntoView(false);
element.scrollIntoView({block: "end"});
element.scrollIntoView({behavior: "instant", block: "end", inline: "nearest"});
```

