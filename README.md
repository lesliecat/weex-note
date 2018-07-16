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

## less 不要加注释，打包会有问题

## storage
> * storage.setItem可以存储对象，getItem得到的是字符串


## div v-if 放在第一层，值为false会有问题
> * 不放在第一层，或加v-else 输出空div

## 定位问题
> * fixed 父元素的内边距有影响
> * 位置在上面的绝对定位的元素，放在上面，否则在显示隐藏时会有问题

* weex 不支持z-index，靠后的元素层级最高
* // Weex本身以750定宽方式做整体缩放，iPhonex因比例并非常规iPhone比例，需要去除多余的145px，以访问安全区域，参考：
      // https://www.zhihu.com/question/67400176
      // https://github.com/zwwill/blog/issues/15
      // https://yq.aliyun.com/articles/134276?utm_content=m_26383
      // https://lybeen.me/2017/07/30/weex-ui-adaptive/