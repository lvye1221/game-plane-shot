# game-plane-shot



# ΢�ŷɻ���ս #

���ֻ���ק����


# �ƶ������ʵ��ҳ����ק #

```

// ������ק
startTouch: function() {

	var self = this;
	
	console.log("startTouch");
		
	// ע����������ʽ������¼�
	this.ele.addEventListener('touchstart', function(e) {
		console.log("ontouchstart");
		
		e = e.touches[0];
		
		var disX = e.clientX - self.ele.offsetLeft;
		var disY = e.clientY - self.ele.offsetTop;
		
		document.addEventListener('touchmove', function(e) {
			e = e.touches[0];
			
			var x = e.clientX - gameEngine.ele.offsetLeft - disX;
			var y = e.clientY - disY;
			
			console.log("ontouchmove��", x, y);
			
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



# �ƶ���ҳ���ֹ�϶�ҳ�� #
