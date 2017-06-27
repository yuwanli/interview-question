interview
===========================
该文件主要是汇总一些前端面试会遇到的一些问题，以及一些自己的见解和看法。
***
### HTML5新增了哪些内容或API，使用过哪些
```
1、用于绘画的 canvas 元素及相关的canvas的API
2、用于媒介回放的 video 和 audio 元素
3、对本地离线存储的更好的支持(storage)
4、语意化更好的内容元素，比如 article、footer、header、nav、section
5、新的表单控件，比如 calendar、date、time、email、url、search
6、本地数据库
```
***
### input和textarea的区别
```
1、一个是单行文本框不可换行，一个是多行文本框可换行
2、`input`的值是放在`value`中，`textarea`的值是放在标签中间的
```
***
### 用一个div模拟textarea的实现(http://www.zhangxinxu.com/study/201012/div-textarea-height-auto.html)
CSS代码：
```css
.test_box {
    width: 400px;
    min-height: 120px;
    max-height: 300px;
    _height: 120px;
    margin-left: auto;
    margin-right: auto;
    padding: 3px;
    outline: 0;
    border: 1px solid #a0b3d6;
    font-size: 12px;
    word-wrap: break-word;
    overflow-x: hidden;
    overflow-y: auto;
    -webkit-user-modify: read-write-plaintext-only;
}
```

HTML代码：
```html
<div class="test_box" contenteditable="true"><br /></div>
```

JS代码：
```js
if (typeof document.webkitHidden == "undefined") {
    // 非chrome浏览器阻止粘贴
    box.onpaste = function() {
        return false;
    }
}
```

### 左右布局：左边定宽、右边自适应
```
1、左边设置左浮动，右边宽度设置100%(或者设置`margin-left`)
2、flex布局
3、通过css3的`calc()`算出右边容器的具体宽度
```

### css3的新特性
```
1、新增选择器（常用的有属性选择器、子元素选择器）
2、圆角、阴影、渐变
3、背景边框的相关属性`background-size` `background-clip` `border-image`
4、变形及位移
5、动画
```

### BFC、IFC、GFC、FFC(http://www.cnblogs.com/dingyufenglian/p/4845477.html)
```
1、BFC(Block Formatting Contexts)直译为"块级格式化上下文"。Block Formatting Contexts就是页面上的一个隔离的渲染区域，容器里面的子元素不会在布局上影响到外面的元素，反之也是如此。如何产生BFC？
> float的值不为none
 overflow的值不为visible
 position的值不为relative和static
2、IFC(Inline Formatting Contexts)直译为"内联格式化上下文"，IFC的line box（线框）高度由其包含行内元素中最高的实际高度计算而来（不受到竖直方向的padding/margin影响)
3、GFC(GridLayout Formatting Contexts)直译为"网格布局格式化上下文"，当为一个元素设置display值为grid的时候，此元素将会获得一个独立的渲染区域，我们可以通过在网格容器（grid container）上定义网格定义行（grid definition rows）和网格定义列（grid definition columns）属性各在网格项目（grid item）上定义网格行（grid row）和网格列（grid columns）为每一个网格项目（grid item）定义位置和空间。
4、FFC(Flex Formatting Contexts)直译为"自适应格式化上下文"，display值为flex或者inline-flex的元素将会生成自适应容器（flex container），可惜这个牛逼的属性只有谷歌和火狐支持，不过在移动端也足够了，至少safari和chrome还是OK的，毕竟这俩在移动端才是王道。
```

### 如何居中
```
1、`margin:auto`实现水平居中
2、`text-algin:center`水平居中
3、`display:table-cell`需添加一层空元素用于`display:table`，然后`text-align: center; vertical-align:middle;`
4、`position`和`transform`实现居中
5、`flex` 布局实现居中
```




