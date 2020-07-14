<script>
	export default {
		// 全局变量
		globalData:{
			text:""
		},
		onLaunch: function() {
			console.log('App Launch')
			uni.$on('Message', function(e){
				console.log(e)
				// // 通知分类页修改数据
				if(e.from && e.from == "index"){
					uni.$emit('index',e)
				 }
			})
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	/* 官方ui库 */
	@import "/common/uni.css";
	/* 第三方动画库 */
	@import "/common/animate.css";
	/* 自定义图标库 */
	@import "/common/iconfont.css";
	/* UI基础库 */
	@import "/common/zcm-main.css";
	/* 公共样式 */
	@import "/common/common.css";
</style>
