<template>
	<!-- 三图广告位  左边w:373 h530 右边w:373 h262-->
	<view class="d-flex ">
		<image :src="resdata.big.src" mode="widthFix" 
		lazy-load style="width: 373upx;height: 530upx; border-right: 2upx solid #F5F5F5;"
		@tap="event(resdata.big)"></image>
		<view class="d-flex flex-column" style="border-left: 2upx solid #F5F5F5;">
			<image :src="resdata.smalltop.src" mode="widthFix" 
			style="height: 262upx; width: 373upx; height: 262upx; border-bottom: 2upx solid #F5F5F5;"
			@tap="event(resdata.smalltop)"></image>
			<image :src="resdata.smallbottom.src" 
			mode="widthFix" style="height: 262upx; width: 373upx; height: 262upx; border-top: 2upx solid #F5F5F5;"
			@tap="event(resdata.smallbottom)"></image>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			resdata: Object
		},
		methods:{
			event(obj){
				console.log(obj)
			}
		}
	}
</script>

<style>
</style>
