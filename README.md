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
			console.log(data);
			if(data.status == 'success'){
				// var art_link = ;
				// location.href = art_link;
				console.log(data);
				alert('success');
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

/*两行省略*/
width:100%;
color: #000000;
overflow: hidden;
display: -webkit-box;
-webkit-line-clamp: 2;
-webkit-box-orient: vertical;
word-break: break-all;

-webkit-box-sizing:border-box;内边框


WeixinJSBridge.invoke('closeWindow',{},function(res){
				alert(res.err_msg);
				alert('关闭本页面！');
			});


//判断手机号
		function isPhone(phone){
			var myreg = /^(((13[0-9]{1})|(14[0-9]{1})|(17[0]{1})|(15[0-3]{1})|(15[5-9]{1})|(18[0-9]{1}))+\d

{8})$/;
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