# game-plane-shot



# 微信飞机大战 #

用手机拖拽着玩


# 移动端如何实现页面拖拽 #

```

// 触摸拖拽
startTouch: function() {

	var self = this;
	
	console.log("startTouch");
		
	// 注意得用这个方式来添加事件
	this.ele.addEventListener('touchstart', function(e) {
		console.log("ontouchstart");
		
		e = e.touches[0];
		
		var disX = e.clientX - self.ele.offsetLeft;
		var disY = e.clientY - self.ele.offsetTop;
		
		document.addEventListener('touchmove', function(e) {
			e = e.touches[0];
			
			var x = e.clientX - gameEngine.ele.offsetLeft - disX;
			var y = e.clientY - disY;
			
			console.log("ontouchmove：", x, y);
			
			if (x < 0) {
				x = 0;
			}
			
			if (x > gameEngine.ele.offsetWidth - self.ele.offsetWidth) {
				x = gameEngine.ele.offsetWidth - self.ele.offsetWidth;
			}
			
			self.ele.style.left = x + "px";
			self.ele.style.top = y + "px";
		});
		
		document.addEventListener('touchup', function() {
			document.removeEventListener('touchmove');
			document.removeEventListener('touchup');
		});
	});
},
	
```



# 移动端页面禁止拖动页面 #
