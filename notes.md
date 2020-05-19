## 布局

1. 正常布局流(Normal flow) ，浏览器默认的HTML布局方式。
2. 弹性盒子(Flexbox)：Flexbox用于设计横向或纵向的布局。
3. Grid布局：设计用于同时在两个维度上把元素按行和列排列整齐。

下列技术会改变默认的布局行为

1. display
   1. value
   2. block
   3. inline
   4. inline-block
2. 浮动-float
3. position-默认值是static
4. 表格布局
5. 多列布局

## 浮动float

浮动会改变元素本身和正常布局流中跟随它的其他元素行为，这一元素会浮动到左侧或右侧，并且从正常布局流中移除，这时候其他的周围内容就会在这个被设置浮动的元素周围环绕。

1. `left` — 将元素浮动到左侧。
2. `right` — 将元素浮动到右侧。
3. `none` — 默认值, 不浮动。
4. `inherit` — 继承父元素的浮动属性。

## 定位技术

1. 静态定位：是每个元素默认的属性——它表示“将元素放在文档布局流的默认位置——没有什么特殊的地方”。
2. 相对定位：允许我们相对于元素在正常的文档流中的位置移动它——包括将两个元素叠放在页面上。这对于微调和精准设计(design pinpointing)非常有用。
3. 绝对定位：将元素完全从页面的正常布局流(normal layout flow)中移出，类似将它单独放在一个图层中。我们可以将元素相对于页面的 `` 元素边缘固定，或者相对于该元素的*最近被定位祖先元素(nearest positioned ancestor element)*。绝对定位在创建复杂布局效果时非常有用，例如通过标签显示和隐藏的内容面板或者通过按钮控制滑动到屏幕中的信息面板。
4. 固定定位：与绝对定位非常类似，但是它是将一个元素相对浏览器视口固定，而不是相对另外一个元素。 这在创建类似在整个页面滚动过程中总是处于屏幕的某个位置的导航菜单时非常有用。
5. 粘性定位：是一种新的定位方式，它会让元素先保持和`position: static`一样的定位，当它的相对视口位置(offset from the viewport)达到某一个预设值时，他就会像`position: fixed`一样定位,它将默认的静态定位(static positioning)和固定定位(fixed positioning)相混合。

## 表格布局

表格布局的缺点在于不够灵活，繁重的标记，难以调试和语义上的错误（比如，屏幕阅读器用户在导航表布局方面有问题）。

## 多列布局

多列布局模组给了我们 一种把内容按列排序的方式，就像文本在报纸上排列那样。由于在web内容里让你的用户在一个列上通过上下滚动来阅读两篇相关的文本是一种非常低效的方式，那么把内容排列成多列可能是一种有用的技术。

要把一个块转变成多列容器(multicol container)，我们可以使用 [`column-count`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/column-count)属性来告诉浏览器我们需要多少列，也可以使用[`column-width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/column-width)来告诉浏览器以至少某个宽度的尽可能多的列来填充容器。

### 改变多列样式

1. 使用 [`column-gap`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/column-gap) 改变列间间隙。
2. 用 [`column-rule`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/column-rule) 在列间加入一条分割线。

### 液态网络

液态网络属于弹性的网格，随着浏览器的iewport大小的变化自动伸缩。为了达成这个目标，需要把

固定宽度转为伸缩的基于百分比宽度的算式

```
target / context = result
假设目标列长度是60像素，上下文是960像素，可以这样计算百分比
60 / 960 = 0.0625
然后移动小数点后两位，得到百分数6/25%
```

