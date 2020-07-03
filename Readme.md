前言：
开发流程：1、环境搭建->2、项目创建->3、App.vue引入全局公共样式->4、底部导航开发->5、UI基础封装->6、首页开发(VUe部分)->7、nvue基础快速入门
	->8、首页开发Nvue部分->9、搜索页开发->10、搜索列表开发->11、商品分类页开发->12、商品详情也开发->13、商品评论页开发->14、vue快速掌握
	->15、购物车开发->16、个人中心开发->17、设置首页开发->18、编辑个人资料页开发->19、收货地址开发->20、订单页开发->21、订单支付页开发->22、发票页开发
	->23、登陆页开发->24、通知页开发->25、通知详情页开发->26、优化首次加载页面白屏问题->27、支付方式页和支付成功页开发->28、选择优惠券页开发
	->29、订单详细页开发->30、物流信息页开发->31、申请售后页开发->32、关于商城页开发->33、前后端交互部分开发->34、多端兼容处理->31、多端兼容处理
	->35、打包上线->36、后端部署
1、环境搭建：略
2、项目创建：https://uniapp.dcloud.io/frame?id=%e7%9b%ae%e5%bd%95%e7%bb%93%e6%9e%84
3、App.Vue 引入全局公共样式
	1.1、引入样式库
		uni.css 	//官方ui库
		animate.css //css动画库
		icon.css 	//图标库
		common.css 	//公共样式
	1.2、解决uni.css第五行找不到uni.ttf报错
	将uni.ttf拷贝到static目录下即可解决
	1.3、解决iconfont.css中.iconfont报错
	font-family: "iconfont"  , sans-serif  !important;
4、在pages.json中配置tabBar
5、常用样式封装：1、颜色、背景颜色、边框颜色、文本颜色，2、布局，3、边框，4、内边距，5、外边距，6字体大小，7行高，8、flex布局 。 详情见zcm-main.css，commmon.css
6、全局组件引用：需要到main.js中才能引入全局组件
	import divider from "@/components/common/divider.vue"
	//注册全局组件
	Vue.component('divider',divider)



HBuilder使用技巧：
同时按住Ctrl+Alt+Shift，鼠标拖动，可以跨行选中同一个位置