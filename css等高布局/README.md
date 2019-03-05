<h2>css等高布局的方式</h2>
参考：https://www.cnblogs.com/xiaohuochai/p/5457127.html

```
在工作中经常有这种需求，左边的div的高度会随着右边的div的内容的增加而增加，右边div的高度也会随着左边div的内容的增加而增加。
下面记一下实现的方法：
```

1.**负margin**
```
思路：
    设置一个大数值的padding-bottom，再设置相同数值的负的margin-bottom
```
- [注意]如果页面中使用 a标签锚点跳转时，将会隐藏部分文字信息

- [注意]如果页面中的背景图片定位到底部，将会看不到背景图片
```css
<style>
body,p{margin: 0;}
.parent{
    overflow: hidden;
    background-color: lightgrey;
}
.left,.centerWrap,.right{
    float: left;
    width: 50%;
    padding-bottom: 9999px;
    margin-bottom: -9999px;
    background-color: pink;
}
.center{
    margin: 0 20px;
}
.left,.right{
    width: 25%;
    background-color: lightblue;
}
</style>
```
```html
<div class="parent">
    <div class="left">
      <p>left</p>
    </div>
    <div class="centerWrap">
      <div class="center">
        <p>center</p>
        <p>center</p>
      </div>
    </div>
    <div class="right">
        <p>right</p>
    </div>
</div>
```
2.**display:table-cell**
```
会使元素表现的类似一个表格中的单元格td,td默认就是等高的
```
- [注意] 不要与float：left; position:absolute; 一起使用 
- [注意] margin设置无效，响应padding设置
- [注意] 不要对display：table-cell使用百分比设置宽度和高度
```css
<style>
  .left,.right{
    border:1px solid #ccc;
    width: 200px;
    display: table-cell;
  }
  </style>
```
```html
<div class="parent">
  <div class="left">
    <p>12345667</p>
    <p>30092888</p>
    <p>hhhhhhhh</p>
  </div>

  <div class="right">
    <p>hahahha</p>
  </div>
</div>
```
table-cell其他的拓展应用：<br/>https://blog.csdn.net/messagebox_/article/details/82380913