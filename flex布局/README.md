<h2>flex布局</h2>
小青蛙游戏练习flex布局： https://flexboxfroggy.com/ <br/>
参照：https://juejin.im/post/5c74935c6fb9a049fc042bd6

```
   弄清楚分别写在容器（让容器有能力让子项目能够改变其宽度、高度，
甚至顺序）、子项目身上的属性。（与之前的盒模式不同的是，之前的父元素由子元素撑开，现在的父元素宽高决定子元素宽高，有兼容问题。）
```

<h3>一、flex-container</h3>

1.**display:flex;**

```
  将父元素设置为弹性盒模型，内部的元素默认全部在主轴方向一行显示,不换行。
```

2.**flex-direction：设置父元素主轴（对齐）方向**

```
决定主轴(一般是x轴)的方向，即项目排列的方向，有四个可能的值：row(默认)| row-reverse | column | column-reverse
```

- row:主轴为水平方向，项目沿主轴从左至右排列
- column：主轴为竖直方向，项目沿主轴从上至下排列
- row-reverse：主轴水平，项目从右至左排列，与row反向
- column-reverse：主轴竖直，项目从下至上排列，与column反向

<a href="">举个栗子</a>

3.**flex-wrap设置子项目换行:**

```
   默认情况下，item排列在一条线上，即主轴上，flex-wrap决定当排列不下时,
是否换行以及换行的方式，可能的值nowrap(默认) | wrap | wrap-reverse
```

- nowrap：自动缩小项目，不换行
- wrap：换行，且第一行在上方
- wrap-reverse：换行，第一行在下面

4.**flex-flow总写:column wrap**

```
是flex-direction和flex-wrap的简写形式，
如：row wrap | column wrap-reverse等。
默认值为row nowrap，即横向排列 不换行。
```

```css
.flex-container{
    flex-flow: row nowrap;
}
```

5.**justify-content：子项目在父元素的主轴对齐方向**

```
非常重要，决定item在主轴上的对齐方式，可能的值有flex-start（默认），flex-end，center，space-between，space-around。
```

<p>当主轴沿水平方向时，具体含义为</p>

- flex-start：左对齐
- flex-end：右对齐
- center：居中对齐
- space- between：两端对齐
- space-around：沿轴线均匀分布

<p>备注： 当项目item布满父节点item-container时，flex-start, flex-end不起到作用</p>

6.**align-items:子项目在父元素中的侧轴对齐方向（没换行的）**
<p>当主轴水平(Y轴)时，其具体含义为：</p>

- flex-start：顶端对齐
- flex-end：底部对齐
- center：竖直方向上居中对齐
- baseline：item第一行文字的底部对齐
- stretch：默认值，拉伸，当item未设置高度时，item将和容器等高对齐
<p>备注：父节点flex-container与子节点flex-item存在高度差，才能起到作用</p>

7.**align-content:6）子项目在父元素中的侧轴对齐方向（有换行的）**

- Center中间
- Flex-end主轴方向的最后位置
- Flex-start主轴方法的最初起点
- Space-between（常用，间隔开空白地方）
- Space-around（空白地方围绕）

<h3>二、flex-item</h3>

1.**order的值是整数，默认0，整数越小，item排列越靠前**
```css
.flex-container{
    flex-flow: wrap;
}
.flex-items{
  order:1;
}
```

2.**flex-grow**
```
定义了当flex容器有多余空间时，item是否放大。默认值为0，即当有多余空间时也不放大；可能的值为整数，表示不同item的放大比例
```
备注：item项目未规定宽度，则分配一行宽度，即使规定了宽度也分配多余空间

3.**flex-shrink**
```
定义了当容器空间不足时，item是否缩小。默认值为1，表示当空间不足时，item自动缩小，其可能的值为整数，表示不同item的缩小比例。
```

4.**flex-basis**
```
表示项目在主轴上占据的空间，默认值为auto。
```

5.**flex**
```
flex属性是flex-grow、flex-shrink和flex-basis三属性的简写总和
```

6.**align-self**
```
align-self属性允许item有自己独特的在交叉轴上的对齐方式，它有六个可能的值，默认值为auto
```

- auto：和父元素align-self的值一致
- flex-start：顶端对齐
- flex-end：底部对齐
- center：竖直方向上居中对齐
- baseline：item第一行文字的底部对齐
- stretch：当item未设置高度时，item将和容器等高对齐

