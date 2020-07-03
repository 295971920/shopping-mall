<template>
		<!-- 图标分类组件开发 -->
		<view class="row p2 j-center m-2">
			<block v-for="(item,index) in resdata" :key="index">
				<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1 " hover-class="btn__hover" @tap="event(item)">
					<image :src="'/static/images/indexnav/'+ item.src" mode="widthFix"
					style="width: 60upx; height: 60upx;" ></image>
					<text class="font-sm">{{item.text}}</text>
				</view>
			</block>
		</view>
</template>

<script>
	export default {
		props: {
			resdata: Array
		},
		methods:{
			event(item){
				console.log("点击了图标分类组件")
				console.log(item)
			}
		}
	}
</script>

<style>
</style>
<!-- 上面使用循环替换了这些原始数据 -->
<!-- <view>
		<view class="row p2 j-center m-2">
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/1.png" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">新品分类</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/2.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">小米众筹</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/3.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">以旧换新</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/4.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">1分拼团</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/5.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">超值特卖</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/6.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">小米秒杀</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/7.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">真心想要</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/8.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">电视热卖</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/9.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">家电热卖</text>
			</view>
			<view class="span-4 text-center p4 d-flex flex-column j-center a-center py-1">
				<image src="@/static/images/indexnav/10.gif" mode="widthFix"
				style="width: 60upx; height: 60upx;" ></image>
				<text class="font-sm">米粉卡</text>
			</view>
		</view>
	</view> -->