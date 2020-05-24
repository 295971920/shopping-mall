<template>
	<view>
		<!-- 水平布局 display: inline-block; 将元素放到一行 -->
		<view style="line-height: 1; display: inline-block; background: #0056B3; width: 185.5upx; height: 150upx; border-right:2upx solid #FFFFFF;"></view>
		<view
			style="line-height: 1; display: inline-block; background: #007BFF;  width: 187.5upx; height: 150upx; border-left: 2upx solid #FFFFFF; border-right: 2upx solid #FFFFFF;"
		></view>
		<view style="line-height: 1; display: inline-block; background: #A71D2A;  width: 371upx; height: 150upx; border-left: 2upx solid #FFFFFF;"></view>

		<!-- 水平滚动 -->
		<scroll-view scroll-x class="scroll-row">
			<view style="width: 200upx;" class="border scroll-row-item text-center">1</view>
			<view style="width: 200upx;" class="border scroll-row-item text-center">2</view>
			<view style="width: 200upx;" class="border scroll-row-item text-center">3</view>
			<view style="width: 200upx;" class="border scroll-row-item text-center">4</view>
			<view style="width: 200upx;" class="border scroll-row-item text-center">5</view>
			<view style="width: 200upx;" class="border scroll-row-item text-center">6</view>
		</scroll-view>
		
		<!-- 布局 -->
		<view class="row p-2">
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				1
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				2
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				3
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				4
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				5
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				6
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				7
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				8
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				9
			</view>
			<view class="span-4 text-center py-2">
				<view class="iconfont icon-VIP"></view>
				10
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	onLoad() {},
	methods: {}
};
</script>

<style></style>
