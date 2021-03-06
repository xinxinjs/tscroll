# tScroll

Javascript滚动条插件2.0

支持纵向横向滚动拖动和各种自定义配置，思路基于jquery.tinyscrollbar.js

效果详见 [Demo](http://travisup.com/demo/plugins/tscroll/demo.html)

### Usage
	
##### tScroll(selector, options)

调用方法，第一个参数可以参数元素本身、`#id` 或 `.class`，第二个参数是配置项，可不传。如下：
    
    var sb = tScroll('.demo');

##### .update(scroll)

使用过程中，由于主体内容变化导致高度或宽度改变，可以通过该方法重置滚动条。传入的参数为一个数值（单位px），也可以是字符串 `'bottom'`直接滚到底部，不传维持原有高度。如下：

	sb.update(0);

##### .moveTo(scroll)

该方法可以直接让滚动到指定位置，传入的参数为数值（单位px）。如下：

	sb.moveTo(100);

##### .setting(options)

如果开始的时候没有传入配置，中途也是可以重新改的，调用该方法后，还是必须重新调用 `update()` 方法才能使新配置生效。

	var options = {
		axis: 'x',
		scroll: false
	};
	sb.setting(options);
	sb.update();

##### .scroll/.wheel/.direction

滚动的长度/速度/属性（top/left），只提供访问，不允许修改。

    sb.scroll

该版本的节点为自动生成，提供一套样式。

### Options

插件提供可配置的选项，调用方法如下：
    
    var options = {
			axis: 'x',
			scroll: false
		};
	    sb = tScroll('.demo', options);
	
    
* `scroll`：是否绑定滚轮事件，默认`true`
* `wheel`: 滚动速度，传入数值，默认`40`
* `axis`: 滚动轴方向，可选 `x` 横轴或 `y` 纵轴，默认`y`
* `trackSize`: 滚动条高度，传入数值，默认`auto`
* `thumbSize`: 滚动条滑块高度，传入数值，膜`auto`
* `thumbMinSize`: 滚动条滑块最小高度，当`thumbSize`为`auto`生效，默认`10`
* `lockScroll`: 是否锁定滚动事件，如果为`true`,滚动事件不传递给父级，默认为`true`
* `invertScroll`: 移动设备反转效果，默认为`false`
* `onSelect`: ie低版本下的兼容措施，`body`的`onselectstart`由于有些情况可能需要用到这个属性，故给个配置选项可以取消插件对这个属性的操作，默认为`true`，指插件可以操作该属性
* `bounce`: 是否启用超出反弹效果，多用于移动设备
* `callback`: 滚动回调函数，传入第一个参数为自己

### Author

[Travis](http://travisup.com/)

