# weex-note

* overflow:hidden 在 Android 上是默认行为

## 默认flex布局 div
> * flex 默认排列方式，flex-direction: column，从上到下，主轴是y轴

## background
> * 不能使用background简写
> * background-color 有效
> * background: red; 无效

## 事件的穿透现象
> * 浮层不加事件，点击会触发浮层下面元素的事件
> * 给浮层加 @touchstart="preventDefault"
> * ios 没有这个问题

## less 不要加注释，打包会有问题

## storage
> * storage.setItem可以安卓可以存储对象，getItem得到的是字符串，ios不行
> * 为了统一，存储字符串格式或number
> * getItem 是异步的


## div v-if 放在第一层，值为false会有问题
> * 不放在第一层，或加v-else 输出空div
> * template 第一次div 默认高度100%，flex-direction: 默认; 竖排width 100%;height: 内容高度
flex-direction: row;横排，height: 100%; width: 内容宽度

## 定位问题
> * 位置在上面的绝对定位的元素，放在上面，否则在显示隐藏时会有问题
> * 定位局中，position: absolute; left: 0; right: 0; text-align: center; top: 10px; left 和right要设置，否则ios不会局中

## ref用变量表示，取值方法
> * :ref="'zanIcon'+moment.feedId"
> * this.$refs[`zanIcon${feedId}`][0]


## scroller
> * 直接加scroller，div超出屏幕会滚动，不加，不会滚动

## text 
> * 超出加省略号 lines: 1; text-overflow: ellipsis;


## web
> * 查询字符串  JOSN.stringify 转化的  要用encodeURIComponent  转码  否则ios不识别

## text 不可换行写

## 前进和返回
> * 前进用 jumpTo 有历史记录
> * 返回用  jumpBack

## weex不支持v-show

## 注意点
> * 模版里（template）最外层标签只能用<div>标签来表示，其他标签都会报错
> * 在写Css样式时，必须使用类名或者ID进行设置，其他选择器不起作用。
> * 我们在weex中<input>标签必须写成闭合形式,例如<input/>。如果不闭合在手机或者模拟器中是渲染不出来的，会一直显示加载。
> * div组件和text组件都不支持背景图片
> * 宽：720px=100%         高：1250px =100%
> * <list>就相当于我们在html中的<ul>标签。<cell>就相当于我们在html中的<li>标签。需要注意的是并不需要给<list>和<cell>增加额外的css样式，而是把样式都写在<div>中，还有就是在网页中预览的时候会出现一些样式错误，但是你在模拟器中预览就比较好。

## opacity
> * ios给父元素加opacity，只能影响父元素，不影响子元素。安卓正常
> * bindingX 设置opacity 能影响子元素

## height
> * 安卓设置 height:0; 没有作用，改成1,ios没有这个问题







* weex 不支持z-index，靠后的元素层级最高
* // Weex本身以750定宽方式做整体缩放，iPhonex因比例并非常规iPhone比例，需要去除多余的145px，以访问安全区域，参考：
      // https://www.zhihu.com/question/67400176
      // https://github.com/zwwill/blog/issues/15
      // https://yq.aliyun.com/articles/134276?utm_content=m_26383
      // https://lybeen.me/2017/07/30/weex-ui-adaptive/