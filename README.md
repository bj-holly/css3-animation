# css3-animation

<pre>

CSS3动画的属性主要分为三类：transform、transition以及animation。

一、transform

	1、rotate		设置元素顺时针旋转的角度，用法是：
			
					transform: rotate(x);		参数x必须是以deg结尾的角度数或0，可为负数表示反向。

	2、scale		设置元素放大或缩小的倍数，用法包括：

					transform: scale(a);		元素x和y方向均缩放a倍
					transform: scale(a, b);	元素x方向缩放a倍，y方向缩放b倍
					transform: scaleX(a);		元素x方向缩放a倍，y方向不变
					transform: scaleY(b);		元素y方向缩放b倍，x方向不变
	
	3、translate	设置元素的位移，用法包括：

					transform: translate(a, b);		元素x方向位移a，y方向位移b
					transform: translateX(a);		元素x方向位移a，y方向不变
					transform: translateY(b);		元素y方向位移b，x方向不变

	4、skew			设置元素倾斜的角度，用法包括：

					transform: skew(a, b);	元素x方向逆时针倾斜角度a，y方向顺时针倾斜角度b
					transform: skewX(a);		元素x方向逆时针倾斜角度a，y方向不变
					transform: skewY(b);		元素y方向顺时针倾斜角度b，想方向不变
											以上的参数均必须是以deg结尾的角度数或0，可为负数表示反向。

	5、matrix		设置元素的变形矩阵，因为矩阵变形过于复杂，暂略。
	
	6、origin		设置元素的悬挂点，用法包括：

					transform-origin: a b;	元素的悬挂点为(a, b)
											元素的悬挂点即为它旋转和倾斜时的中心点。取值中的a、b可以是长度值、以%结尾的百分比或者left、top、right、bottom四个值。


二、transition

	1、transition-property			指定transition效果作用的CSS属性，其值是CSS属性名。
	2、transition-duration			动画效果持续的时间，其值为以s结尾的秒数。
	3、transition-timing-function		指定元素状态的变化速率函数，其取值基于贝赛尔曲线函数。
	4、transition-delay				动画效果推迟开始执行的时间，其值为以s结尾的秒数。
									PS：transition: property duration timing-function delay;
									
									transition-timing-function:
									linear		规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。
									ease		规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。
									ease-in		规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。
									ease-out	规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。
									ease-in-out	规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。
									cubic-bezier(n,n,n,n)	在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。


三、animation	CSS3中真正的动画属性是animation，而前面的transform和transition都只是对DOM元素的变形或者是状态的过渡。实际上，CSS3所支持的动画效果只是填充动画，也就是说先设定整个动画生命周期中的几个关键状态（key  frame，关键帧），然后动画将自行计算并模拟关键帧之间的过渡。那么在设置animation的属性之前就必须先设定好关键帧了。
	

	1、@keyframes name{

			a% {
		         /*CSS属性*/
	         }

		    b% {
				/*CSS属性*/
			}
			...
		}

	2、animation					所有动画属性的简写属性，除了 animation-play-state 属性。		
	
	3、animation-name				规定 @keyframes 动画的名称。
	
	4、animation-duration			规定动画完成一个周期所花费的秒或毫秒。默认是 0。
	
	5、animation-timing-function	规定动画的速度曲线。默认是 "ease"。
									linear	动画从头到尾的速度是相同的。	
									ease	默认。动画以低速开始，然后加快，在结束前变慢。
									ease-in	动画以低速开始。	
									ease-out	动画以低速结束。	
									ease-in-out	动画以低速开始和结束。	
									cubic-bezier(n,n,n,n)	在 cubic-bezier 函数中自己的值。可能的值是从 0 到 1 的数值。

	6、animation-delay				规定动画何时开始。默认是 0。

	7、animation-iteration-count	规定动画被播放的次数。默认是 1。
									n	定义动画播放次数的数值。	
									infinite	规定动画应该无限次播放。

	8、animation-direction			规定动画是否在下一周期逆向地播放。默认是 "normal"。
									normal	默认值。动画应该正常播放。	
									alternate	动画应该轮流反向播放。
	
	9、animation-play-state			规定动画是否正在运行或暂停。默认是 "running"。您可以在 JavaScript 中使用该属性，这样就能在播放过程中暂停动画。
									paused	规定动画已暂停。
									running	规定动画正在播放。
									
	10、animation-fill-mode			规定对象动画时间之外的状态。
									forwards	当动画完成后，保持最后一个属性值（在最后一个关键帧中定义）。
									backwards	在 animation-delay 所指定的一段时间内，在动画显示之前，应用开始属性值（在第一个关键帧中定义）。
									both	向前和向后填充模式都被应用。
				

四、前缀

	因为CSS3还没有正式发布，所以各种浏览器对它的支持也不尽相同。
	所以在设置CSS3属性（包括@开头的新属性）的时候通常需要对其添加浏览器标识的前缀，
	-webkit- 表示Webkit内核的浏览器Chrome和Safari，
	-moz- 表示FireFox，
	-o- 表示Opera。
	无视IE吧，在IE上的实现通常还是要用到滤镜，而不是CSS3。

</pre>