# ImageEditor
ImageEditor是一个依赖jQuery，Hammer.js的插件，基于HTML5的canvas，可以实现图片的放大、旋转、移动，并将多个图像合并。 并且支持手机多点触控。
### 使用方法
```js
var options = {
	imageUrls: [
		{url: '../public/images/pic-2.jpg', closeButtonRequire: false},
		{url: '../public/images/background-1.png', closeButtonRequire: false, clickToSelect: false, onClick: function() { editor.selectImage(0);}},
		'../public/images/mustache.png'
	],
	width: 300,
	height: 300,
	onInitCompleted: function() {
		editor.selectImage(0); // 选中最底部的图像进行编辑
	}
},
editor = $('#editor').ImageEditor(options); // 初始化
```

### Public methods
```js
editor.moveImage(deltaX, deltaY); // 移动图像
editor.rotateImage(90); // 图像旋转90度
editor.scaleImage(1.5); // 放大1.5倍
editor.addImage(urlObj, true); // 添加图片并且设置为选中状态（可编辑）。
editor.setImage(urlObj, 1, false); // 替换index=1的图像
editor.removeImage(2); // remove index = 2 的图像
editor.removeAll(); // remove 所有 图像
editor.reset(); // ImageEditor创建后重置为初始状态
editor.mergeImage(); // 合成图片，并且return 一个canvas。
```

### Demo
http://demo.jackyang.me/image-editor/app/demo.html
