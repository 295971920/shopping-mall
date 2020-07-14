<template>
	<view>
		<button type="primary" @click="ceshi">修改首页数据</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				ceshiText: 'ceshi'
			}
		},
		methods: {
			ceshi(){
				// 用于获取当前页面栈的实例，以数组形式按栈的顺序给出，第一个元素为首页，最后一个元素为当前页面。
				let pages = getCurrentPages();
				// 可以得到当前webview的对象实例，从而实现对 webview 更强大的控制
				let index = pages[0].$getAppWebview();
				console.log(index.id)
				uni.$emit("plusMessage",{
					res:this.ceshiText
				},index.id)
				// 关闭当前页面
				uni.navigateBack();
			}
		}
	}
</script>

<style>

</style>
