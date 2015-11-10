# QuickTest
快测app：简而言之是一款测试app的android app，当时制作目的，只是想将繁复的PC测试转移至移动端，简单化。
<img src="https://github.com/FzuLiWei/QuickTest/blob/master/main.png"/>

主要分为四个功能，Android手机需要Root，请在测试前先使用kingroot等软件一键root.

<b>(1)遍历测试：</b>
		针对软件应用的控件遍历测试，包括控件点击、控件滑动操作，测试完成后会自动过滤日志，查找崩溃信息，并生成控件映射节点，帮助开发快速定位Bug控件。

		报告demo: http://test.99.com/QuickTest/QuickTestReport?taskid=558 

		实现原理：基于Android原生的uiautomator. 
		1.暂时只支持Native App,不支持H5及混合应用; 
		2.支持自动登陆功能,但需用户提供登录的账号密码; 
		3.由于Android机型及应用的复杂度,若要使用自动登录功能,请详细阅读遍历测试登陆F&Q; 
		4.若开启截屏功能,程序会在操作控件时截图,能直接定位崩溃时操作的控件;
		5.若开启弱网络功能,可以模似弱网络场景下的应用表现.
		6.可以系统设置邮箱，测试完后自动推送至邮箱。
		
		<img src="https://github.com/FzuLiWei/QuickTest/blob/master/traversal.gif"/>
		
<b>(2)应用监控：</b>

		针对测试人员在手工测试过程中的应用监控；
		
		1、	日志监控：若应用在手工测试过程中发生崩溃，测试完成后会自动导出崩溃日志，追踪应用崩溃；
		2、	性能监控：在设置界面开启“快测球”, 可以在手工测试过程中查看时时性能数据，包括CPU、内存、手机帧数；
		3、	开启截屏功能后，会根据用户的操作触发手机截屏，与性能数据形成一对一映射。
		4、	开启弱网络功能后，可以模似弱网络场景下的应用表现.
		
		<img src="https://github.com/FzuLiWei/QuickTest/blob/master/performance.gif"/>

<b>(3)稳定性测试：</b>

		针对测试应用的稳定性，分软件与游戏两种测试方式；
		
		1、	软件测试：使用Android 的Monkey工具，同时增加模糊测试功能（基于Intent Fuzzer，给应用组件发送Null Intent，来检测APP是否崩溃）。
		2、	游戏测试：实现原理基于图像引擎,模糊识别控件,生成更有效的点击序列;更准确的触发游戏功能,保证游戏稳定性测试的范围.
		
		<img src="https://github.com/FzuLiWei/QuickTest/blob/master/stability.png"/>
		
<b>(4)录制回放：</b>

		录制用户的操作，生成脚本，并在回放脚本时，追踪应用BUG信息。
		
		录制功能：采用录制屏幕触摸事件，即录制用户手势及坐标操作，有一定的局限性。适用场景:复杂手势的游戏录制。
		PS：结束录制快捷键,+-音量键即可结束录制。

		回放功能：在脚本仓库里选择已录制的脚本进行回放，同时在回放结束后会自动解析日志。
		
		<img src="https://github.com/FzuLiWei/QuickTest/blob/master/record.png"/>
		
<b>遍历测试登陆F&Q</b>

		1.适用范围：系统版本在4.1至4.4的设备；
		2.登录功能不支持验证码输入；
		3.系统版本为4.1、4.2，若登录按钮是图片，无法保证登录功能正常完成；
		4.部分应用与机型，在输入框已存在账号密码时，不能全选，容易影响登录功能的正常运行，建议这种情况先清除已输的账号密码；
		5.为确保登录功能正常，请用原生输入法或百度输入法、谷歌键盘，并设置成英文全键盘模式。部分机型（oppo中有发现）的原生输入法存在输入问题（重复输入现象）；
		6.键盘需设置成正常键盘，浮动键盘影响点击效果；
		7.部分机型（oppo中有发现）存在纯净后台模式，遍历功能无法使用；
 
<b>设置</b>

		1、	设置邮箱：设置后测试记录都会推送至指定邮箱；
		2、	设置99u：99u是网龙公司内部IM，仅限公司内部人员可用,设置后会将结果推送至指定99u账号或群组；
		3、	开启快测球：在应用监控功能，可以时时查看性能数据；
		4、	显示系统应用：在选择测试应用选项，默认为只显示第三方应用，若是Android ROM的系统应用测试人员，可勾选会显示Android系统应用；
		5、	仅WIFI下联网：在测试完成后，程序会自动同步测试记录至后台，默认仅在WIFI情况下同步，防止手机流量浪费。

		<img src="https://github.com/FzuLiWei/QuickTest/blob/master/setting.png"/>
		
		
<b>二维码</b>
		
		扫描下方二维码关注快测app最新动态
		<img src="https://github.com/FzuLiWei/QuickTest/blob/master/code.jpg"/>
		


