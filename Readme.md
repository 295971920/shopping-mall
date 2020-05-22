1、App.Vue 引入全局公共样式
	1.1、引入样式库
		uni.css 	//官方ui库
		animate.css //css动画库
		icon.css 	//图标库
		common.css 	//公共样式
2、解决uni.css第五行找不到uni.ttf报错
	将uni.ttf拷贝到static目录下即可解决
3、解决iconfont.css中.iconfont报错
	font-family: "iconfont"  , sans-serif  !important;
