# weex-note
weex笔记
* overflow:hidden 在 Android 上是默认行为
* flex 默认排列方式，flex-direction: column
 从上到下，主轴是y轴
* background-color 有效
  background: red; 无效
 不难使用background简写
* weex 不支持z-index，靠后的元素层级最高
* // Weex本身以750定宽方式做整体缩放，iPhonex因比例并非常规iPhone比例，需要去除多余的145px，以访问安全区域，参考：
      // https://www.zhihu.com/question/67400176
      // https://github.com/zwwill/blog/issues/15
      // https://yq.aliyun.com/articles/134276?utm_content=m_26383
      // https://lybeen.me/2017/07/30/weex-ui-adaptive/