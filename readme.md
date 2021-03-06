# Swiper

<a href="https://github.com/nolimits4web/swiper" target="_blank">Swiper Github</a>  
<a href="http://www.idangero.us/swiper" target="_blank">Swiper HomePage</a>

本模块基于Swiper@3.2制作，详细Api文档请访问<a href="http://www.idangero.us/swiper/api" target="_blank">[Swiper Api]</a>  
功能和 [Swipe](https://github.com/Aimeejs/swipe) 类似，区别在于```Swipe```更轻量，未压缩版只有19KB，但功能不如```Swiper```丰富  
追求极致性能的webapp ```Swipe```是你的选择，追求极致功能的客户端```Swiper```是你的选择


#### Install
```
aimee i swiper
```

### Register
```javascript
// init.js 注册到全局模块
aimee.reg('swiper');
```

#### Example
下面示例dom中的类必须存在，样式已打包到模块中，无需手动添加
```html
<div class="swiper-container">
	<div class="swiper-wrapper">
		<div class="swiper-slide">
			<img src="images/1.jpg", alt="">
		</div>
		<div class="swiper-slide">
			<img src="images/2.jpg", alt="">
		</div>
		<div class="swiper-slide">
			<img src="images/3.jpg", alt="">
		</div>
	</div>
</div>
```

因为此模块涉及到尺寸位置计算，所以需要在```page```或者```app```渲染到浏览器之后调用，  
Aimeejs app内应该在 ```app.pagerender``` 方法之内调用，  
Aimeejs page内应该在 ```page.postrender``` 方法之内调用
```javascript
$('.swiper-container').swiper()
```

or
```javascript
$('.swiper-container').swiper({
	// 设定初始化时slide的索引，默认为0
	initialSlide: 0,

	// Slides的滑动方向，可设置水平(horizontal)或垂直(vertical)
	direction: horizontal,

	// 滑动速度，即slider自动滑动开始到结束的时间（单位ms）
	speed: 300

	// 自动切换的时间间隔（单位ms），不设定该参数slide不会自动切换。
	autoplay: 0,

	// 是否开启循环
	loop: false,

	// 用户操作swiper之后，是否禁止autoplay。默认为true：停止。
	// 如果设置为false，用户操作swiper之后自动切换不会停止，每次都会重新启动autoplay。
	// 操作包括触碰，拖动，点击pagination等。
	autoplayDisableOnInteraction: true,

	// 设置为true时，鼠标覆盖Swiper时指针会变成手掌形状，拖动时指针会变成抓手形状。（根据浏览器形状有所不同）
	grabCursor: true,

	// Swiper从3.0开始使用flexbox布局(display: flex)，开启这个设定会在Wrapper上添加等于slides相加的宽高，在对flexbox布局的支持不是很好的浏览器中可能需要用到。
	setWrapperSize: false,

	// 宽度设置
	width: 600,

	// 高度设置
	height: 400,

	// 设定为true将slide的宽和高取整(四舍五入)以防止某些分辨率的屏幕上文字模糊。
	roundLengths: true
})
```