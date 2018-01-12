# flex-style
flex兼容写法

## 1.兼容性
![安卓真机上测试结果](http://p0.meituan.net/education/018539331feb4d9cf0bdb609b14678c0122349.png)

测试结果：
1. android从4.4版本开始支持flex
1. android 4.0~4.3 部分支持-webkit-flex，另一部分不支持
1. 测试中发现奇葩机器华为6.0以下（不包含6.0）也不支持flex
下面是通过CanIUse中得出
1. safari 7.1以下只支持box，7.1+支持-webkit-flex
1. IE10以下不支持box，10+支持-ms-flex

总的来说，想实现弹性布局，需要同时使用box和flex


## 2.兼容写法：
```
/* flex 容器 */
.flexbox {
    display: -webkit-box;
    display: -moz-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
}
/* 元素垂直从上到下排列 */
.flex-vertical {
    -moz-box-orient: vertical;
    -webkit-box-orient: vertical;
    -webkit-flex-direction: column;
    flex-direction: column;
}
/* 元素垂直从下到上排列 */
.flex-vertical {
    -webkit-box-pack: end;
    -webkit-box-direction: reverse;
    -webkit-box-orient: vertical;
    -moz-flex-direction: column-reverse;
    -webkit-flex-direction: column-reverse;
    flex-direction: column-reverse;
}
/* 元素水平从左到右排列 */
.flex-horizontal {
    -moz-box-orient: horizontal;
    -webkit-box-orient: horizontal;
    -webkit-flex-direction: row;
    flex-direction: row;
}
/* 元素水平从右到左排列 */
.flex-horizontal-reverse {
    -webkit-box-pack: end;/* box-direction只改变方向，需要box-pack改版对齐方式 */
    -webkit-box-direction: reverse;
    -webkit-box-orient: horizontal;
    -moz-flex-direction: row-reverse;
    -webkit-flex-direction: row-reverse;
    flex-direction: row-reverse;
}
.flex-1 {
    -moz-box-flex: 1;
    -webkit-box-flex: 1;
    -webkit-flex: 1;
    flex: 1;
}
.flex-2 {
    -moz-box-flex: 1;
    -webkit-box-flex: 2;
    -webkit-flex: 2;
    flex: 2;
}
.flex-3 {
    -moz-box-flex: 1;
    -webkit-box-flex: 3;
    -webkit-flex: 3;
    flex: 3;
}

/* align-items：垂直交叉轴的对齐方式 */
.flex-align-start {
    -moz-box-align: start;
    -webkit-box-align: start;
    -webkit-align-items: flex-start;
    align-items: flex-start;
}
.flex-align-center {
    -moz-box-align: center;
    -webkit-box-align: center;
    -webkit-align-items: center;
    align-items: center;
}
.flex-align-end {
    -moz-box-align: end;
    -webkit-box-align: end;
    -webkit-align-items: flex-end;
    align-items: flex-end;
}
.flex-align-stretch {
    -moz-box-align: stretch;
    -webkit-box-align: stretch;
    -webkit-align-items: stretch;
    align-items: stretch;
}
.flex-align-baseline {
    -moz-box-align: baseline;
    -webkit-box-align: baseline;
    -webkit-align-items: baseline;
    align-items: baseline;
}

/* justify-content：主轴的对齐方式 */
.mb-flex-justify-start {
    -moz-box-pack: start;
    -webkit-box-pack: start;
    -webkit-justify-content: flex-start;
    justify-content: flex-start;
}
.mb-flex-justify-center {
    -moz-box-pack: center;
    -webkit-box-pack: center;
    -webkit-justify-content: center;
    justify-content: center;
}
.mb-flex-justify-end {
    -moz-box-pack: end;
    -webkit-box-pack: end;
    -webkit-justify-content: flex-end;
    justify-content: flex-end;
}
.mb-flex-justify-space-between {
    -moz-box-pack: justify;
    -webkit-box-pack: justify;
    -webkit-justify-content: space-between;
    justify-content: space-between;
}

```

## 3.参考资料：
- [flex布局兼容性问题](http://www.cnblogs.com/mk2016/p/5562994.html)
- [阮一峰-Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
- [阮一峰-Flex 布局教程：实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

## 4.最后
![flex脑图](http://p0.meituan.net/education/712a0612bb2fc23630cc1bd952947014344805.png)