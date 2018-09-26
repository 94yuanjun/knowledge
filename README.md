# knowledge
一些常用知识点
<script src="<?php echo JS_URL;?>jquery-2.0.3.min.js"></script> 导入jq库
PHP explode 切割字符串
js for  forin
php的数组不能直接js调用，要先json_encode()转成json， 再eval转成数组
php数组存的时候  arr[]=xxxx
<link rel="stylesheet" href="<?php echo STATIC_URL; ?>investigate/index.css" type="text/css" />  引入外部css
placeholder="请输入..."  输入框第一次显示 请输入。。
.val 取<value="">

$.ajax({
		type: 'POST',
		url: '/investigate/writedata',
		data: {data:data,id:<?php echo $id; ?>},
		dataType: 'json',
		success: function(data){
			if(data.status == 'success'){
				alert(data.msg);
			}else{
				alert(data.msg);
			}
		}
	});

box-shadow:[inset] x-offset y-offset blur-radius spread-radiuscolor      阴影（ 有上下左右阴影 ）box-shadow: 上,右 ,下 ,左
textarea 文本框多行  input输入框单行    placeholder=“请输入。。。” 
 window.prompt（）确认框

对于HTML元素本身就带有的固有属性，在处理时，使用prop方法。
对于HTML元素我们自己自定义的DOM属性，在处理时，使用attr方法。
INT((ACOS(SIN(B1/180*PI())*SIN(B2/180*PI())+COS(B1/180*PI())*COS(B2/180*PI())*COS(A1/180*PI()-A2/180*PI()))*180*60/PI())

*100000)/100000*1.852 两经纬度之间距离
object.prototype.name=value prototype 属性使您有能力向对象添加属性和方法。
<body ontouchmove="event.preventDefault()"> 取消事件的默认动作。
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no"> 禁止缩放
/data/www/admin/protected/config 添加分类的表

/*一行表示**/
overflow: hidden;
white-space: nowrap;
text-overflow: ellipsis;
/***2行表示**/
display: -webkit-box;
overflow: hidden;
text-overflow: ellipsis;
word-wrap: break-word;
white-space: normal !important;
-webkit-line-clamp: 2;
-webkit-box-orient: vertical;

-webkit-box-sizing:border-box;内边框


WeixinJSBridge.invoke('closeWindow',{},function(res){
				alert(res.err_msg);
				alert('关闭本页面！');
			});


//判断手机号
		function isPhone(phone){
			var myreg = /^(((13[0-9]{1})|(14[0-9]{1})|(17[0]{1})|(15[0-3]{1})|(15[5-9]{1})|(18[0-9]{1}))+\d{8})$/;
			if(phone == ''){
				// message = "手机号码不能为空！";
				return false;
			}else if(phone.length !=11){
				// message = "请输入有效的手机号码！";
				return false;
			}else if(!myreg.test(phone)){
				// message = "请输入有效的手机号码！";
				return false;
			}else{
				return true;
			}
		}

	//判断身份证
		function isCardID(sId){
			var aCity={11:"北京",12:"天津",13:"河北",14:"山西",15:"内蒙古",21:"辽宁",22:"吉林",23:"黑龙

江",31:"上海",32:"江苏",33:"浙江",34:"安徽",35:"福建",36:"江西",37:"山东",41:"河南",42:"湖北",43:"湖南",44:"广东",45:"广西

",46:"海南",50:"重庆",51:"四川",52:"贵州",53:"云南",54:"西藏",61:"陕西",62:"甘肃",63:"青海",64:"宁夏",65:"新疆",71:"台

湾",81:"香港",82:"澳门",91:"国外"} 
			var iSum=0 ;
			var info="" ;
			//你输入的身份证长度或格式错误
			if(!/^\d{17}(\d|x)$/i.test(sId)) return false;
			sId=sId.replace(/x$/i,"a");
			//你的身份证地区非法
			if(aCity[parseInt(sId.substr(0,2))]==null) return false;
			sBirthday=sId.substr(6,4)+"-"+Number(sId.substr(10,2))+"-"+Number(sId.substr(12,2));
			var d=new Date(sBirthday.replace(/-/g,"/")) ;
			//"身份证上的出生日期非法"
			if(sBirthday!=(d.getFullYear()+"-"+ (d.getMonth()+1) + "-" + d.getDate()))return false;
			for(var i = 17;i>=0;i --) iSum += (Math.pow(2,i) % 11) * parseInt(sId.charAt(17 - i),11) ;
			//"你输入的身份证号非法"
			if(iSum%11!=1) return false;
			//aCity[parseInt(sId.substr(0,2))]+","+sBirthday+","+(sId.substr(16,1)%2?"男":"女");//此次还可以判

断出输入的身份证号的人性别
			return true;
		}


<input type="text" name="tel" value=""/>
<textarea type="text" name="helpInfo" placeholder="请输入...">
resize: none;固定大小



　　 /^\\d+$/　　　　　　　　　　//非负整数（正整数 + 0） 
　　/^[0-9]*[1-9][0-9]*$/　　　 //正整数 
　　/^((-\\d+)|(0+))$/　　　    //非正整数（负整数 + 0） 
　　/^-[0-9]*[1-9][0-9]*$/　　  //负整数 
　　/^-?\\d+$/　　　　　　　　   //整数 
　　/^\\d+(/　　　　　　　　　 //非负浮点数（正浮点数 + 0） 
　　/^(([0-9]+\\.[0-9]*[1-9][0-9]*)|([0-9]*[1-9][0-9]*\\.[0-9]+)|([0-9]*[1-9][0-9]*))$/　　　　//正浮点数 
　　/^((-\\d+(/　　　　　　　　   //非正浮点数（负浮点数 + 0） 
　　/^(-(([0-9]+\\.[0-9]*[1-9][0-9]*)|([0-9]*[1-9][0-9]*\\.[0-9]+)|([0-9]*[1-9][0-9]*)))$/　　  //负浮点数 
　　/^(-?\\d+)(/　　　　　　　　 //浮点数



echo "<script> addHtml('{$item["nickname"]}','{$item["reply"]}','{$k}','{$item["review"]}','{$item["nickname"]}'); 

</script>";在php中加js，以及拼接php  用.!!!!

<iframe frameborder=0 name="back" style="width:100%;min-height:100%;"></iframe>点击之后同一页显示数据

explode("",string) 切割字符串变成数组

history.back(-1):直接返回当前页的上一页，数据全部消息，是个新页面

history.go(-1):也是返回当前页的上一页，不过表单里的数据全部还在

/* background:-webkit-linear-gradient(top,#99b5dc,#fff); */

box-sizing: border-box;内边框

<link rel="stylesheet" href="<?php echo STATIC_URL; ?>mqrz/css/index/detail.css" type="text/css" />
		<script src="<?php echo JS_URL;?>jquery-2.0.3.min.js"></script>
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-

scalable=no"/>
/*placeholder色值*/ 
textarea::-webkit-input-placeholder { /* WebKit browsers */ 
color: #000; 
} 
textarea:-moz-placeholder { /* Mozilla Firefox 4 to 18 */ 
color: #000; 
} 
textarea::-moz-placeholder { /* Mozilla Firefox 19+ */ 
color: #000; 
} 
textarea:-ms-input-placeholder { /* Internet Explorer 10+ */ 
colo r: #000; 
} 

initial设置属性为其默认值
inherit	从父元素继承属性

css3动画
@keyframes name
{
	from {top:1rem;}
	to {top:3rem;}
}
animation: name duration timing-function delay iteration-count direction fill-mode play-state; 

animation-name	指定要绑定到选择器的关键帧的名称
animation-duration	动画指定需要多少秒或毫秒完成（加S）
animation-timing-function	设置动画将如何完成一个周期
linear	动画从头到尾的速度是相同的。	
ease	默认。动画以低速开始，然后加快，在结束前变慢。	
ease-in	动画以低速开始。	测试
ease-out	动画以低速结束。	
ease-in-out	动画以低速开始和结束。	
cubic-bezier(n,n,n,n)	在 cubic-bezier 函数中自己的值。可能的值是从 0 到 1 的数值。

animation-delay	设置动画在启动前的延迟间隔。（加S）
animation-iteration-count	定义动画的播放次数。n次数 infinite无穷
animation-direction	指定是否应该轮流反向播放动画。
normal正常播放
reverse反向播放
alternate动画在奇数次（1、3、5...）正向播放，在偶数次（2、4、6...）反向播放。
alternate-reverse动画在奇数次（1、3、5...）反向播放，在偶数次（2、4、6...）正向播放。

animation-fill-mode	规定当动画不播放时（当动画完成时，或当动画有一个延迟未开始播放时），要应用到元素的样式。
none 不执行 默认
forwards 在动画结束后（由 animation-iteration-count 决定），动画将应用该属性值。
backwards 动画将应用在 animation-delay 定义期间启动动画的第一次迭代的关键帧中定义的属性值。这些都是 from 关键帧中的值（当 

animation-direction 为 "normal" 或 "alternate" 时）或 to 关键帧中的值（当 animation-direction 为 "reverse" 或 "alternate-

reverse" 时）。	
both 动画遵循 forwards 和 backwards 的规则。也就是说，动画会在两个方向上扩展动画属性。

animation-play-state	指定动画是否正在运行或已暂停。
paused	指定暂停动画
running	指定正在运行的动画

	<link rel="stylesheet" href="<?php echo STATIC_URL; ?>vrepair/css/index.css" type="text/css" />
	<script src="<?php echo JS_URL;?>jquery-2.0.3.min.js"></script>
	<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
	<meta name="apple-mobile-web-app-capable" content="yes">
	<meta name="apple-mobile-web-app-status-bar-style" content="black">
	<meta name="format-detection" content="telephone=no">
	<script src="<?php echo STATIC_URL; ?>vrepair/js/wuxianup.js" type="text/javascript"></script>

vertical-align 属性设置元素的垂直对齐方式。
父元素要设置line-height
使用元素要是inline-block和inline

!important优先级更高

clip-path:polygon(0 0,calc(100% - 4rem) 0,calc(100% - 4rem) 3.5rem,100% 3.5rem,100% 100%,0 100%)//不规则矩形 里面是xy坐标
clip-path:circle(30px at 35px 35px)//圆
clip-path:circle(65px 30px at 125px 40px)//椭圆
clip:rect(top,right,bottom,left)//因为只能剪裁矩形所以基本被弃用了
//隐藏滚动轴
::-webkit-scrollbar{
  display:none;
}
//背景图固定
background-image: url(); 
  background-attachment: fixed;
 
需使用的自定义光标的 URL。
注释：请在此列表的末端始终定义一种普通的光标，以防没有由 URL 定义的可用光标。
cursor:crosshair;
default	默认光标（通常是一个箭头）
auto	默认。浏览器设置的光标。
crosshair	光标呈现为十字线。
pointer	光标呈现为指示链接的指针（一只手）
move	此光标指示某对象可被移动。
e-resize	此光标指示矩形框的边缘可被向右（东）移动。
ne-resize	此光标指示矩形框的边缘可被向上及向右移动（北/东）。
nw-resize	此光标指示矩形框的边缘可被向上及向左移动（北/西）。
n-resize	此光标指示矩形框的边缘可被向上（北）移动。
se-resize	此光标指示矩形框的边缘可被向下及向右移动（南/东）。
sw-resize	此光标指示矩形框的边缘可被向下及向左移动（南/西）。
s-resize	此光标指示矩形框的边缘可被向下移动（南）。
w-resize	此光标指示矩形框的边缘可被向左移动（西）。
text	此光标指示文本。
wait	此光标指示程序正忙（通常是一只表或沙漏）。
help	此光标指示可用的帮助（通常是一个问号或一个气球）

//滤镜
filter: grayscale(100%);
none	默认值，没有效果。
blur(px)	给图像设置高斯模糊。"radius"一值设定高斯函数的标准差，或者是屏幕上以多少像素融在一起， 所以值越大越模糊；

如果没有设定值，则默认是0；这个参数可设置css长度值，但不接受百分比值。
brightness(%)	给图片应用一种线性乘法，使其看起来更亮或更暗。如果值是0%，图像会全黑。值是100%，则图像无变化。其他的值对应线性乘数效果。值超过100%也是可以的，图像会比原来更亮。如果没有设定值，默认是1。
contrast(%)	调整图像的对比度。值是0%的话，图像会全黑。值是100%，图像不变。值可以超过100%，意味着会运用更低的对比。若没有设置值，默认是1。
drop-shadow(h-shadow v-shadow blur spread color)	
给图像设置一个阴影效果。阴影是合成在图像下面，可以有模糊度的，可以以特定颜色画出的遮罩图的偏移版本。 函数接受<shadow>(在CSS3背景中定义)类型的值，除了"inset"关键字是不允许的。该函数与已有的box-shadow box-shadow属性很相似；不同之处在于，通过滤镜，一些浏览器为了更好的性能会提供硬件加速。<shadow>参数如下：
<offset-x> <offset-y> (必须)
这是设置阴影偏移量的两个 <length>值. <offset-x> 设定水平方向距离. 负值会使阴影出现在元素左边. <offset-y>设定垂直距离.负值会使阴影出现在元素上方。查看<length>可能的单位.
如果两个值都是0, 则阴影出现在元素正后面 (如果设置了 <blur-radius> and/or <spread-radius>，会有模糊效果).
<blur-radius> (可选)
这是第三个code><length>值. 值越大，越模糊，则阴影会变得更大更淡.不允许负值 若未设定，默认是0 (则阴影的边界很锐利).
<spread-radius> (可选)
这是第四个 <length>值. 正值会使阴影扩张和变大，负值会是阴影缩小.若未设定，默认是0 (阴影会与元素一样大小). 
注意: Webkit, 以及一些其他浏览器 不支持第四个长度，如果加了也不会渲染。
 
<color> (可选)
查看 <color>该值可能的关键字和标记。若未设定，颜色值基于浏览器。在Gecko (Firefox), Presto (Opera)和Trident (Internet Explorer)中， 会应用colorcolor属性的值。另外, 如果颜色值省略，WebKit中阴影是透明的。
grayscale(%)	
将图像转换为灰度图像。值定义转换的比例。值为100%则完全转为灰度图像，值为0%图像无变化。值在0%到100%之间，则是效果的线性乘子。若未设置，值默认是0；
hue-rotate(deg)	
给图像应用色相旋转。"angle"一值设定图像会被调整的色环角度值。值为0deg，则图像无变化。若值未设置，默认值是0deg。该值虽然没有最大值，超过360deg的值相当于又绕一圈。
invert(%)	
反转输入图像。值定义转换的比例。100%的价值是完全反转。值为0%则图像无变化。值在0%和100%之间，则是效果的线性乘子。 若值未设置，值默认是0。
opacity(%)	
转化图像的透明程度。值定义转换的比例。值为0%则是完全透明，值为100%则图像无变化。值在0%和100%之间，则是效果的线性乘子，也相当于图像样本乘以数量。 若值未设置，值默认是1。该函数与已有的opacity属性很相似，不同之处在于通过filter，一些浏览器为了提升性能会提供硬件加速。
saturate(%)	
转换图像饱和度。值定义转换的比例。值为0%则是完全不饱和，值为100%则图像无变化。其他值，则是效果的线性乘子。超过100%的值是允许的，则有更高的饱和度。 若值未设置，值默认是1。
sepia(%)	
将图像转换为深褐色。值定义转换的比例。值为100%则完全是深褐色的，值为0%图像无变化。值在0%到100%之间，则是效果的线性乘子。若未设置，值默认是0；
url()	
URL函数接受一个XML文件，该文件设置了 一个SVG滤镜，且可以包含一个锚点来指定一个具体的滤镜元素。
例如：
filter: url(svg-url#element-id)

//允许拖动
startDrag(obj, obj);

网页可见区域宽：document.body.clientWidth 
网页可见区域高：document.body.clientHeight 
网页可见区域宽：document.body.offsetWidth (包括边线的宽) 
网页可见区域高：document.body.offsetHeight (包括边线的宽)  
网页正文全文宽：document.body.scrollWidth 
网页正文全文高：document.body.scrollHeight  
网页被卷去的高：document.body.scrollTop 
网页被卷去的左：document.body.scrollLeft 
网页正文部分上：window.screenTop 
网页正文部分左：window.screenLeft 
屏幕分辨率的高：window.screen.height 
屏幕分辨率的宽：window.screen.width 
屏幕可用工作区高度：window.screen.availHeight 
屏幕可用工作区宽度：window.screen.availWidth
//display:none 的时候获取的高度有问题

！function(){}() , (function(){})() , (function(){}()) , new function(){} , void function(){}();封装时候用的匿名函数

多张图片上传的时候input一定要加name  $_File才能取到值

php""会执行内部变量 ''不会执行   换行PHP_EOL

pointer-events: none;取消点击事件

//离开页面
window.onbeforeunload=function (){
alert("===onbeforeunload===");
if(event.clientX>document.body.clientWidth && event.clientY < 0 || event.altKey){
     alert("你关闭了浏览器");
}else{
     alert("你正在刷新页面");
}
}

监听浏览器返回键、后退、上一页事件（popstate）操作返回键
window.addEventListener("popstate", function(){
    //doSomething
}, false)

substr_replace(string,replacement,start,length)
string	必需。规定要检查的字符串。
replacement	必需。规定要插入的字符串。
start	
必需。规定在字符串的何处开始替换。
正数 - 在第 start 个偏移量开始替换
负数 - 在从字符串结尾的第 start 个偏移量开始替换
0 - 在字符串中的第一个字符处开始替换
charlist	
可选。规定要替换多少个字符。
正数 - 被替换的字符串长度
负数 - 从字符串末端开始的被替换字符数
0 - 插入而非替换


一、校验数字的表达式

1 数字：^[0-9]*$

2 n位的数字：^\d{n}$

3 至少n位的数字：^\d{n,}$

4 m-n位的数字：^\d{m,n}$

5 零和非零开头的数字：^(0|[1-9][0-9]*)$

6 非零开头的最多带两位小数的数字：^([1-9][0-9]*)+(.[0-9]{1,2})?$

7 带1-2位小数的正数或负数：^(\-)?\d+(\.\d{1,2})?$

8 正数、负数、和小数：^(\-|\+)?\d+(\.\d+)?$

9 有两位小数的正实数：^[0-9]+(.[0-9]{2})?$

10 有1~3位小数的正实数：^[0-9]+(.[0-9]{1,3})?$

11 非零的正整数：^[1-9]\d*$ 或 ^([1-9][0-9]*){1,3}$ 或 ^\+?[1-9][0-9]*$

12 非零的负整数：^\-[1-9][]0-9"*$ 或 ^-[1-9]\d*$

13 非负整数：^\d+$ 或 ^[1-9]\d*|0$

14 非正整数：^-[1-9]\d*|0$ 或 ^((-\d+)|(0+))$

15 非负浮点数：^\d+(\.\d+)?$ 或 ^[1-9]\d*\.\d*|0\.\d*[1-9]\d*|0?\.0+|0$

16 非正浮点数：^((-\d+(\.\d+)?)|(0+(\.0+)?))$ 或 ^(-([1-9]\d*\.\d*|0\.\d*[1-9]\d*))|0?\.0+|0$

17 正浮点数：^[1-9]\d*\.\d*|0\.\d*[1-9]\d*$ 或 ^(([0-9]+\.[0-9]*[1-9][0-9]*)|([0-9]*[1-9][0-9]*\.[0-9]+)|([0-9]*[1-9][0-9]*))$

18 负浮点数：^-([1-9]\d*\.\d*|0\.\d*[1-9]\d*)$ 或 ^(-(([0-9]+\.[0-9]*[1-9][0-9]*)|([0-9]*[1-9][0-9]*\.[0-9]+)|([0-9]*[1-9][0-9]*)))$

19 浮点数：^(-?\d+)(\.\d+)?$ 或 ^-?([1-9]\d*\.\d*|0\.\d*[1-9]\d*|0?\.0+|0)$

二、校验字符的表达式

1 汉字：^[\u4e00-\u9fa5]{0,}$

2 英文和数字：^[A-Za-z0-9]+$ 或 ^[A-Za-z0-9]{4,40}$

3 长度为3-20的所有字符：^.{3,20}$

4 由26个英文字母组成的字符串：^[A-Za-z]+$

5 由26个大写英文字母组成的字符串：^[A-Z]+$

6 由26个小写英文字母组成的字符串：^[a-z]+$

7 由数字和26个英文字母组成的字符串：^[A-Za-z0-9]+$

8 由数字、26个英文字母或者下划线组成的字符串：^\w+$ 或 ^\w{3,20}$

9 中文、英文、数字包括下划线：^[\u4E00-\u9FA5A-Za-z0-9_]+$

10 中文、英文、数字但不包括下划线等符号：^[\u4E00-\u9FA5A-Za-z0-9]+$ 或 ^[\u4E00-\u9FA5A-Za-z0-9]{2,20}$

11 可以输入含有^%&',;=?$\"等字符：[^%&',;=?$\x22]+

12 禁止输入含有~的字符：[^~\x22]+

三、特殊需求表达式

1 Email地址：^\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$

2 域名：[a-zA-Z0-9][-a-zA-Z0-9]{0,62}(/.[a-zA-Z0-9][-a-zA-Z0-9]{0,62})+/.?

3 InternetURL：[a-zA-z]+://[^\s]* 或 ^http://([\w-]+\.)+[\w-]+(/[\w-./?%&=]*)?$

4 手机号码：^(13[0-9]|14[5|7]|15[0|1|2|3|5|6|7|8|9]|18[0|1|2|3|5|6|7|8|9])\d{8}$

5 电话号码("XXX-XXXXXXX"、"XXXX-XXXXXXXX"、"XXX-XXXXXXX"、"XXX-XXXXXXXX"、"XXXXXXX"和"XXXXXXXX)：^(\(\d{3,4}-)|\d{3.4}-)?\d{7,8}$

6 国内电话号码(0511-4405222、021-87888822)：\d{3}-\d{8}|\d{4}-\d{7}

7 身份证号(15位、18位数字)：^\d{15}|\d{18}$

8 短身份证号码(数字、字母x结尾)：^([0-9]){7,18}(x|X)?$ 或 ^\d{8,18}|[0-9x]{8,18}|[0-9X]{8,18}?$

9 帐号是否合法(字母开头，允许5-16字节，允许字母数字下划线)：^[a-zA-Z][a-zA-Z0-9_]{4,15}$

10 密码(以字母开头，长度在6~18之间，只能包含字母、数字和下划线)：^[a-zA-Z]\w{5,17}$

11 强密码(必须包含大小写字母和数字的组合，不能使用特殊字符，长度在8-10之间)：^(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,10}$

12 日期格式：^\d{4}-\d{1,2}-\d{1,2}

13 一年的12个月(01～09和1～12)：^(0?[1-9]|1[0-2])$

14 一个月的31天(01～09和1～31)：^((0?[1-9])|((1|2)[0-9])|30|31)$

15 钱的输入格式：

16 1.有四种钱的表示形式我们可以接受:"10000.00" 和 "10,000.00", 和没有 "分" 的 "10000" 和 "10,000"：^[1-9][0-9]*$

17 2.这表示任意一个不以0开头的数字,但是,这也意味着一个字符"0"不通过,所以我们采用下面的形式：^(0|[1-9][0-9]*)$

18 3.一个0或者一个不以0开头的数字.我们还可以允许开头有一个负号：^(0|-?[1-9][0-9]*)$

19 4.这表示一个0或者一个可能为负的开头不为0的数字.让用户以0开头好了.把负号的也去掉,因为钱总不能是负的吧.下面我们要加的是说明可能的小数部分：^[0-9]+(.[0-9]+)?$

20 5.必须说明的是,小数点后面至少应该有1位数,所以"10."是不通过的,但是 "10" 和 "10.2" 是通过的：^[0-9]+(.[0-9]{2})?$

21 6.这样我们规定小数点后面必须有两位,如果你认为太苛刻了,可以这样：^[0-9]+(.[0-9]{1,2})?$

22 7.这样就允许用户只写一位小数.下面我们该考虑数字中的逗号了,我们可以这样：^[0-9]{1,3}(,[0-9]{3})*(.[0-9]{1,2})?$

23 8.1到3个数字,后面跟着任意个 逗号+3个数字,逗号成为可选,而不是必须：^([0-9]+|[0-9]{1,3}(,[0-9]{3})*)(.[0-9]{1,2})?$

24 备注：这就是最终结果了,别忘了"+"可以用"*"替代如果你觉得空字符串也可以接受的话(奇怪,为什么?)最后,别忘了在用函数时去掉去掉那个反斜杠,一般的错误都在这里

25 xml文件：^([a-zA-Z]+-?)+[a-zA-Z0-9]+\\.[x|X][m|M][l|L]$

26 中文字符的正则表达式：[\u4e00-\u9fa5]

27 双字节字符：[^\x00-\xff] (包括汉字在内，可以用来计算字符串的长度(一个双字节字符长度计2，ASCII字符计1))

28 空白行的正则表达式：\n\s*\r (可以用来删除空白行)

29 HTML标记的正则表达式：<(\S*?)[^>]*>.*?</\1>|<.*? /> (网上流传的版本太糟糕，上面这个也仅仅能部分，对于复杂的嵌套标记依旧无能为力)

30 首尾空白字符的正则表达式：^\s*|\s*$或(^\s*)|(\s*$) (可以用来删除行首行尾的空白字符(包括空格、制表符、换页符等等)，非常有用的表达式)

31 腾讯QQ号：[1-9][0-9]{4,} (腾讯QQ号从10000开始)

32 中国邮政编码：[1-9]\d{5}(?!\d) (中国邮政编码为6位数字)

33 IP地址：\d+\.\d+\.\d+\.\d+ (提取IP地址时有用)

34 IP地址：((?:(?:25[0-5]|2[0-4]\\d|[01]?\\d?\\d)\\.){3}(?:25[0-5]|2[0-4]\\d|[01]?\\d?\\d))

//返回前一页 判断是否有前一页
function goBack(){
						if(document.referrer==''){
							location.href='http://bhjiguan.wxshidai.com';
						}else{
							window.history.go(-1);
							return false;
						}
					}

input file里面
accept="image/*;capture=camera" 直接调用相机
accept="image/*" 调用相机 图片或者相册

//dirname() 函数返回路径中的目录部分。
require_once(dirname(__FILE__).'/xx.php');
//页面上不能复制的用这个
javascript:document.body.contentEditable='true';document.designMode='on'; void(0);

移动端web禁用长按选中功能
方案一
* {
   -webkit-user-select:none;
   -moz-user-select:none;
   -ms-user-select:none;
   user-select:none;	
}
问题一：这样会让iOS的input框无法聚焦

解决方案：
input{-webkit-user-select:auto;}
问题二：如果需要长按发送语音，禁用长按之后，无法长按发送语音

解决方案：
<div class="voice-speak" ontouchstart="return false;" style="display: none" id="startRecord"><span>按住说话</span></div>

方法二：
禁用点击事件
div { pointer-events: none;}
方法三：
禁用系统默认事件。后期的CLICK不能用了
window.ontouchstart = function(e) { e.preventDefault(); };
