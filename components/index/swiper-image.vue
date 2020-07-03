<template>
		<!-- circular解决最后一张出现空白  不衔接 -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="2000" :duration="1000" circular>
			<block  v-for="(item, index) in resdata" :key="index">
				<swiper-item>
					<view class="swiper-item" @tap="event(item.src)">
						<image :src="item.src" 
						lazy-load style="height: 350upx;"></image>
					</view>
				</swiper-item>
			</block>
		</swiper>
</template>

<script>
export default {
	props: {
		resdata: Array
	},
	methods: {
		event(item){
			console.log("点击了轮播图！"+item)
		}
	}
}
</script>

<style>
</style>
