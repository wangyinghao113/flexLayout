# flexLayout
flex 布局

```
容器的6个属性：
  flex-direction
  flex-wrap
  flex-flow
  justify-content
  align-items
  align-content


flex-direction：
    row（默认）：主轴为水平方向，起点在左端
    row-reverse：主轴在水平方向，起点在右端
    column：主轴为垂直方向，起点在上沿
    column-reverse：主轴为垂直方向，起点在下沿
    
flex-wrap：
    nowrap（默认）：不换行
    wrap：换行，第一行在上方
    wrap-reverse：换行，第一行在下方
    
flex-flow：flex-direction和flex-wrap的简写形式，flex-flow: <flex-direction> || <flex-wrap>;

justify-content：定义项目在主轴上的对其方式
    flex-start（默认）：左对齐
    flex-end：右对齐
    center：居中
    space-between：两端对齐，项目之间的间隔相等
    space-around：每个项目两侧的间隔相等。项目与项目间的间隔，是，项目与边框间的间隔的两倍
    
align-items：定义项目在交叉轴上如何对齐
    flex-start：交叉轴的起点对齐
    flex-end：交叉轴的终点对齐
    center：交叉轴的中点对齐
    baseline：项目的第一行文字的基线对齐
    stretch（默认）：如果项目未设置高度或设为auto，则将占满整个容器
    
align-content：定义了多根轴线的对齐方式。如果只有一根轴线，则该属性不起作用
    flex-start：交叉轴的起点对齐
    flex-end：交叉轴的终点对齐
    center：交叉轴的中点对齐
    space-between：与交叉轴的两端对齐，轴线之间的间隔平均分布
    space-around：每根轴线两侧的间隔相等
    stretch：轴线占满整个交叉轴
    
项目的6个属性：
order：定义项目的排列顺序。数值越小，排列越靠前，默认为0
flex-grow：定义项目的放大比例。默认为0
flex-shrink：定义项目的缩小比例。默认为0
flex-basis：定义在分配多余空间之前，项目占主轴空间。默认为auto
flex：flex-grow/shrink/basis的缩写，flex: none | [flex-grow] [flex-shrink]? || [flex-basis]。两个快捷值：auto（1，1，auto），none（0，0，auto）
align-self：允许单个项目有与其它项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素align-items属性
```
平时项目对flex经常使用的做了简要编写：
```
.flexbox {
    display: -webkit-box !important;
    display: -ms-flexbox !important;
    display: flex !important;

    & > .cell {
        -webkit-box-flex: 1;
        -ms-flex: 1;
        flex: 1;
        flex-basis: auto;
        display: block !important;
        flex-basis: 1px;
        display: -webkit-box !important;
        -webkit-box-align: center;
        -webkit-box-pack: center;
        display: -ms-flexbox !important;
        -ms-flex-pack: center;
        -ms-flex-align: center;
        -webkit-box-orient: vertical;
        -ms-flex-orient: vertical;
        position: relative;

        &.left {
            -webkit-box-align: start;
        }

        &.right {
            -webkit-box-align: end;
        }

        &.top {
            -webkit-box-pack: start;
        }

        &.bottom {
            -webkit-box-pack: end;
        }

        &.ng-hide:not(.ng-hide-animate) {
            display: none !important;
        }

        &.hide {
            display: none !important;
        }
    }

    & > .fixed {
        position: relative;
    }

    &.hide, &.ng-hide:not(.ng-hide-animate) {
        display: none !important;
    }
}
```

详解来自http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool
