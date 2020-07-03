<template>
	<view>
		
		<!-- 顶部选项卡 -->
		<scroll-view scroll-x class="border-bottom scroll-row" style="height: 80rpx;" :scroll-into-view="scrollinto" :scroll-with-animation="true">
			<view class="scroll-row-item px-3" @click="changeTab(index)"
			 style="height: 80rpx; line-height: 80rpx;"
			  v-for="(item,index) in tabBars" :key="index"
			  :class="tabIndex === index ? 'main-text-color':'' "
			  :id="'tab'+index"
			  hover-class="btn__hover border-bottom">
				<text class="font-md">{{item.name}}</text>
			</view>
		</scroll-view>
		
		<!-- 通过获取可视区域高度 解决卡顿问题 -->
		<swiper :duration="150"  :current="tabIndex" :style="'height:'+ scrollH +'px;'" @change="onChangeTab">
			<swiper-item v-for="(item,index) in newsitems" :key="index">
				<scroll-view scroll-y="true" :style="'height:'+ scrollH +'px;'" @scrolltolower="loadmore(index)">
					<block v-for="(list,listIndex) in item.list" :key="listIndex">
						<!-- 轮播图组件 -->
						<swiper-image v-if="list.type === 'swiper'" :resdata="list.data"/>
						
						<template v-else-if="list.type === 'indexnavs' ">
							<!-- 首页图标分类组件开发 -->
							<index-nav :resdata="list.data" />
							<!-- 全局分割线 -->
							<divider />
						</template>
						
						<template v-else-if="list.type === 'threeAdv'">
							<!-- 三图广告组件 -->
							<three-adv :resdata="list.data"/>
							<divider />
						</template>
						
						<!-- 大图广告位 -->
						<!-- <card headTitle="每日精选" bodyCover="/static/images/demo/demo4.jpg" /> -->
												
						<!-- 公共列表组件 750 - 5 = 745   372.5-->
						<view class="row j-sb" v-else-if="list.type === 'list'">
							<block v-for="(item2,index2) in list.data" :key="index2">
								<common-list :item="item2" :index="index2" />
							</block>
						</view>

						<!-- 写基础卡片组件 -->
						<!-- <card :headTitle="card.title" :bodyCover="card.src"></card> -->
						<!-- <card>
							<block slot="title">{{card.title}}</block>
							<image :src="card.src" mode="widthFix"></image>
						</card> -->
						
						<!-- 公共列表组件 750 -5（间隙） = 745  745/2=372.5 -->
						<!-- <view class="row j-sb">
							<block v-for="(item2, index2) in commonList" :key="index2">
								<common-list :item="item2" :index="index2"></common-list>
							</block>
						</view> -->
					</block>
					<!-- 上拉加载更多 -->
					<divider/>
					<view class="d-flex a-center j-center text-light-muted font-md py-3">
						{{item.loadtext}}
					</view>
				</scroll-view>
			</swiper-item>
		</swiper>
		
	</view>
</template>

<script>
	//模拟后端数据
	let demoTabBars = [{
		name: '关注',
		}, {
			name: '推荐',
		}, {
			name: '体育',
		}, {
			name: '热点',
		}, {
			name: '财经',
		}, {
			name: '娱乐',
		}, {
			name: '军事',
		}, {
			name: '历史',
		}, {
			name: '本地',
		}];
	let demo1= [
		{
			type:"swiper",
			data:[
				{ src:"/static/images/demo/demo4.jpg" },
				{ src:"/static/images/demo/demo4.jpg" },
				{ src:"/static/images/demo/demo4.jpg" }
			]
		},
		{
			type:"indexnavs",
			data:[
				{ src: '1.png', text: '新品发布' },
				{ src: '2.gif', text: '小米众筹' },
				{ src: '3.gif', text: '以旧换新' },
				{ src: '4.gif', text: '一分换团' },
				{ src: '5.gif', text: '超值特卖' },
				{ src: '6.gif', text: '小米秒杀' },
				{ src: '7.gif', text: '真心想要' },
				{ src: '8.gif', text: '电视热卖' },
				{ src: '9.gif', text: '家电热卖' },
				{ src: '10.gif', text: '米粉卡' }
			]
		},{
			type:"threeAdv",
			data:{
				big:{
					src:"/static/images/demo/demo1.jpg"
				},
				smalltop:{
					src:"/static/images/demo/demo2.jpg"
				},
				smallbottom:{
					src:"/static/images/demo/demo2.jpg"
				},
			}
		},
		{
			type:"list",
			data:[{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			}]
		}
	];
	let demo2 =[{
			type:"swiper",
			data:[
				{ src:"/static/images/demo/demo4.jpg" },
				{ src:"/static/images/demo/demo4.jpg" },
				{ src:"/static/images/demo/demo4.jpg" }
			]
		},{
			type:"indexnavs",
			data:[
				{ src: '1.png', text: '新品发布' },
				{ src: '2.gif', text: '小米众筹' },
				{ src: '3.gif', text: '以旧换新' },
				{ src: '4.gif', text: '一分换团' },
				{ src: '5.gif', text: '超值特卖' },
				{ src: '6.gif', text: '小米秒杀' },
				{ src: '7.gif', text: '真心想要' },
				{ src: '8.gif', text: '电视热卖' },
				{ src: '9.gif', text: '家电热卖' },
				{ src: '10.gif', text: '米粉卡' }
			]
		},{
			type:"list",
			data:[{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			},
			{
				cover:"/static/images/demo/list/1.jpg",
				title:"米家空调",
				desc:"1.5匹变频",
				oprice:2699,
				pprice:1399
			}]
		}];
import swiperImage from '@/components/index/swiper-image';
import indexNav from '@/components/index/index-nav';
import threeAdv from '@/components/index/three-adv'
import card from '@/components/common/card'
import commonList from '@/components/common/common-list'
export default {
	components: {
		swiperImage,
		indexNav,
		threeAdv,
		card,
		commonList
	},
	data() {
		return {
			scrollinto: "",
			scrollH: 500,
			tabIndex:0,
			tabBars: [],
			newsitems:[]
		}
	},
	onLoad() {
		//获取可视区域高度
		uni.getSystemInfo({
			success: (res) => {
				this.scrollH = res.windowHeight - uni.upx2px(82)
			}
		})
		//初始化事件
		this.__init()
	},
	methods: {
		//初始化事件调用
		__init() {
			//获取顶部选项卡
			this.tabBars = demoTabBars
			//根据顶部选项卡生成页面
			let arr = []
			for (var i = 0;i<this.tabBars.length;i++){
				let obj = {
					list:[],
					// 1、上拉加载更多 2、加载中... 3、没有更多了
					loadtext: "上拉加载更多"
				}
				//获取首屏数据
				if(i=== 0){
					obj.list = demo1
				}
				arr.push(obj)
			}
			this.newsitems = arr
		},
		//切换选项卡
		changeTab(index){
			//如果选中为当前，直接return
			if ( this.tabIndex === index ){
				return ;
			}
			//将当前选中角标传递给tabIndex，使其改变颜色
			this.tabIndex = index
			//选项卡切换时实现联动，使其示出现在可视区域上
			this.scrollinto = 'tab'+index
			//切换时调用addData()方法
			this.addData()
		},
		// 监听滑动列表
		onChangeTab(e){
			// console.log(e)
			this.changeTab(e.detail.current)
		},
		//加载拿到的数据
		addData() {
			//拿到当前索引
			let index = this.tabIndex
			//请求数据库
			this.newsitems[index].list = demo2
		},
		// 上拉加载更多
		loadmore(index){
			let item = this.newsitems[index]
			// 是否处于可加载状态
			if (item.loadtext !== '上拉加载更多' ) return ;
			// 模拟加载
			item.loadtext = '加载中...'
			setTimeout(()=>{
				// 使用...拓展运算符加载数据
				item.list = [ ...item.list, ...demo2 ];
				// 恢复状态
				item.loadtext = '上拉加载更多'
			}, 2000);
		}
	}
}
</script>

<style></style>
