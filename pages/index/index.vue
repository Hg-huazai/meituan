<template>
	<view class="content">
		<!-- 自定义导航 -->
		<!-- <view class="example-body">
			<uni-nav-bar left-icon="arrowleft" right-text="菜单" left-text="返回" title="标题" @clickLeft="back" />
		</view> -->
		<view class="content1">
			<view class="content1-top">
				<!-- <view class="item">
					<navigator class="iconfont icon-gerenzhongxin_xuanzhong-copy" url="../mine/index"></navigator>
				</view>
				<view class="item center" @click="onClickshow">
					<text class="work">
						未开工
					</text>
					<i class="iconfont" :class="icon"></i>
				</view>
				<view class="item right" >
					<i class="iconfont icon-xiaoxi"></i>
					<i class="iconfont icon-lujing"></i>
				</view> -->
				<view class="left-l item">
					<navigator class="iconfont icon-gerenzhongxin_xuanzhong-copy" url="../mine/index"></navigator>
				</view>
				<view class="left-l item center" @click="onClickshow">
					<text class="work">
						未开工
					</text>
					<!-- <i class="iconfont" :class="icon"></i> -->
				</view>
				<view class="right-r item right" >
					<i class="iconfont icon-xiaoxi"></i>
					<i class="iconfont icon-lujing"></i>
				</view>
			</view>
			<!-- -----------------------------------------状态-------------------------------------- -->
			<view class="state">
				<view class="box" :class="[index === curren ? 'active' : '']" v-for="(item,index) in state" :key="index" @tap="statetap(index)">
					<view class="item">
						<text>{{item.name}}</text>
						<i class="iconfont icon-jiantou"></i>
					</view>
				</view>
			</view>
		</view>
		
		
		<!-- -------------------------------------------------弹出--------------------------------------------- -->
		<view class="show" v-bind:style="{display: show}" >
			<view class="bg" @click="onClickbg"></view>
			<view class="show-item">
				<view class="item" @click="onClickwork">
					<i class="iconfont icon-jiedan"></i>
					<text>接单</text>
				</view>
				<view class="item" @click="onClickrest">
					<i class="iconfont icon-kafei xiuxi"></i>
					<text class="">休息</text>
				</view>
			</view>
		</view>
		
		<!-- ----------------------------------------------正文内容 ------------------------------------------------>
		<view class="content2" v-bind:style="{'margin-top':topheight+'px'}">
			<view class="content3">
				<!-- ----------------------------订单------------------------------ -->
				<navigator class="order" url="../details/details">
					<view class="item-top">
						<view class="left-l">
							<i class="iconfont icon-shijian"></i>
							<text>58分钟内送达</text>
						</view>
						<view class="right-r">
							￥<text>17</text>
						</view>
						<view class="clear"></view>
					</view>
					<view class="item-center">
						<view class="left-l left">
							<view class="business-distance">
								<!-- <text>0.5\n</text><text class="text2">km</text> -->
								<view class="text">0.5</view>
								<view class="text2">km</view>
							</view>
							
							<view class="iconfont icon-yuansu_juli"></view>
							
							<view class="guest-distance">
								<!-- <text>4.8\n</text><text class="text2">km</text> -->
								<view class="text">4.8</view>
								<view class="text2">km</view>
							</view>
						</view>
						<view class="left-l right">
							<view class="name">烧鹅王(体育西店)</view>
							<view class="business-address">广州市天河区体育西行街43号</view>
							<view class="guest-address">中华国际中心B座(3601室)</view>
						</view>
						<view class="clear"></view>
					</view>
					<view class="item-bottom">
						<button type="primary">抢单</button>
					</view>
				</navigator>
				<navigator class="order" url="../details/details">
					<view class="item-top">
						<view class="left-l">
							<i class="iconfont icon-shijian"></i>
							<text>58分钟内送达</text>
						</view>
						<view class="right-r">
							￥<text>17</text>
						</view>
						<view class="clear"></view>
					</view>
					<view class="item-center">
						<view class="left-l left">
							<view class="business-distance">
								<!-- <text>0.5\n</text><text class="text2">km</text> -->
								<view class="text">0.5</view>
								<view class="text2">km</view>
							</view>
							
							<view class="iconfont icon-yuansu_juli"></view>
							
							<view class="guest-distance">
								<!-- <text>4.8\n</text><text class="text2">km</text> -->
								<view class="text">4.8</view>
								<view class="text2">km</view>
							</view>
						</view>
						<view class="left-l right">
							<view class="name">烧鹅王(体育西店)</view>
							<view class="business-address">广州市天河区体育西行街43号</view>
							<view class="guest-address">中华国际中心B座(3601室)</view>
						</view>
						<view class="clear"></view>
					</view>
					<view class="item-bottom">
						<button type="primary">抢单</button>
					</view>
				</navigator>
				
			</view>
			
		</view>
		<!-- <view v-bind:style="{ 'margin-top': topheight + 'px' }">666</view> -->
		
		<!-- --------------------------------------------------底部--------------------------------------------------- -->
		<view class="content-bottom">
			<view class="left">
				<view class="iconfont icon-shezhi"></view>
				<view class="name">接单设置</view>
			</view>
			<view class="right">
				<button type="primary">立即开工</button>
			</view>
		</view>
		
		<!-- ----------------------------------------------获得抢单资格---------------------------------------- -->
		<view class="float">
			获得抢单资格
		</view>
	</view>
	
	
</template>

<script>
	import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
	export default {
		components: {
			uniNavBar
		},
		data() {
			return {
				curren: 0,
				topheight: '',
				show: 'none',
				icon: 'icon-jiantou',
				state: [
					{name: "待抢单",state: 1},
					{name: "待取货",state: 2},
					{name: "待送达",state: 3}
				]
			}
		},
		onLoad() {
			var view = uni.createSelectorQuery().select(".content1");
			view.boundingClientRect(data => {
			console.log("节点离页面顶部的距离为" + data.height);
			this.topheight = data.height
			}).exec();
			
			// uni.getSystemInfo({
			// 　　success: function(res) { // res - 各种参数
			// 　　   console.log('屏幕的高度'+res.windowHeight); // 屏幕的宽度 
			
			// 　　    let info = uni.createSelectorQuery().select(".content1");
			// 　　　  　info.boundingClientRect(function(data) { //data - 各种参数
			// 　　　  　console.log('获取元素高度'+ data)  // 获取元素宽度
			// 　　    }).exec()
			//     },
			// });
		},
		methods: {
			statetap(e) {
				this.curren = e ;
			},
			// 点击未开工
			onClickshow (){
				this.show = 'block',
				this.icon = 'icon-jiantou-copy'
				// console.log("show");
			},
			onClickbg (){
				this.show = 'none',
				this.icon = 'icon-jiantou'
			},
			// 接单
			onClickwork (){
				this.show = 'none',
				this.icon = 'icon-jiantou',
				uni.showToast({
				    title: '开始接单了',
				    duration: 2000
				});
				// console.log("接单")
			},
			//休息
			onClickrest (){
				this.show = 'none',
				this.icon = 'icon-jiantou',
				// console.log("休息")
				uni.showToast({
				    title: '您辛苦了',
				    duration: 2000
				});
			}
		}
	}
</script>

<style>
	.float {
		position: fixed;
		right: 0;
		bottom: 150rpx;
		display: inline-block;
		padding: 10rpx 10rpx;
		padding-left: 20rpx;
		border-radius: 30rpx 0  0 30rpx;
		background-color: #ff9600;
		color: #fff;
		font-size: 15rpx;
	}
	.content1 {
		position: fixed;
		top: 0;
		width: 100%;
	}
	.content1-top {
		/* margin-top: 30rpx; */
		padding:50rpx 20rpx 30rpx;
		/* border-top: 35rpx solid #a1a1a1; */
		/* padding: 20rpx; */
		display: flex;
		color: #fff;
		background-color: #21232f;
		/* background: -webkit-linear-gradient(top,#a3a3a3,#21232f); */
	}
	.content1-top .iconfont {
		font-size: 50rpx;
		color: #fff;
	}
	.content1-top .iconfont.icon-jiantou{
		font-size: 30rpx;
		margin-left: 15rpx;
	}
	.content1-top .iconfont.icon-jiantou-copy{
		font-size: 30rpx;
		margin-left: 15rpx;
	}
	.content1-top .item {
		/* flex: 1; */
		width: 33%;
	}
	.content1-top .item.center {
		text-align: center;
	}
	.content1-top .item .work {
		font-weight: bold;
	}
	.content1-top .item.right .icon-lujing {
		float: right;
		
	}
	.content1-top .item.right .icon-xiaoxi {
		float: right;
		margin-left: 30rpx;
	}
	
	/* -------------------------------------------------------状态------------------------------------- */
	.state {
		padding: 20rpx 30rpx;
		display: flex;
		color: #fff;
		background-color: #21232f;
	}
	.state .box {
		text-align: center;
		flex: 1;
		font-size: 32rpx;
		color: #babac2;
	}
	.state .box.active .item {
		border-bottom: 8rpx solid #fff;
		color: #fff;
	}
	.state .box .item{
		padding-bottom: 10rpx;
		display: inline-block;
	}
	.state .box .iconfont{
		font-size: 26rpx;
		margin-left: 20rpx;
	}
	
	/* ----------------------------------------------------------正文----------------------------------------- */
	.content2 {
		/* margin-top: 194rpx; */
		margin-top: 264rpx;
	}
	/*---------------------------------------------------------------------------------底部 */
	.content-bottom {
		position: fixed;
		bottom: 0;
		width: 100%;
		background-color: #FFFFFF;
		border-top: 2rpx solid #dcdcdc;
		padding: 20rpx 30rpx 20rpx 40rpx;
		box-sizing: border-box;
	}
	.content-bottom .left{
		display: inline-block;
		width: 20%;
		text-align: center;
		vertical-align: middle;
	}
	.content-bottom .left .iconfont {
		font-size: 50rpx;
	}
	.content-bottom .left .name {
		font-size: 24rpx;
		color: #000;
		font-weight: bold;
	}
	.content-bottom .right{
		display: inline-block;
		width: 80%;
		text-align: center;
		vertical-align: middle;
	}
	.content-bottom .right button{
		background-color: #fff;
		border: 2rpx solid #d3d3d3;
		border-radius: 60rpx;
		width: 95%;
		color: #000;
		font-weight: bold;
	}
	
	/* -----------------------------------------------------------------------------订单 */
	.order {
		border-top: 20rpx solid #f2f1f7;
		padding: 30rpx 30rpx 20rpx;
		background-color: #FFFFFF;
	}
	.order .item-top {
		margin-bottom: 20rpx;
	}
	.order .item-top .left-l{
		padding-top: 10rpx;
		
	}
	.order .item-top .left-l .iconfont{
		color: #bcbcbc; 
		margin-right: 30rpx;
		font-size: 40rpx;
	}
	.order .item-top .left-l text{
		font-weight: bold;
		font-size: 40rpx;
	}
	.order .item-top .right-r{
		color: #fc5602;
		font-size: 32rpx;
	}
	.order .item-top .right-r text{
		font-size: 50rpx;
		font-weight: bold;
	}
	.order .item-center {
		
	}
	.order .item-center .left-l.left{
		font-size: 20rpx;
		width: 11%;
	}
	.order .item-center .left-l.left .text2{
		font-size: 18rpx;
		color: #999999;
		display: inline-block;
	}
	.order .item-center .left-l.left .iconfont{
		margin-right: 33rpx;
		margin: 20rpx 0;
		margin-left: 5rpx;
	}
	.order .item-center .left-l.left .business-distance {
		font-size: 30rpx;
		text-align: center;
		display: inline-block;
	}
	.order .item-center .left-l.left .guest-distance {
		font-size: 30rpx;
		font-weight: bold;
		text-align: center;
		display: inline-block;
	}
	.order .item-center .left-l.left, .business-distance, .guest-distance text {
		line-height: 30rpx;
	}
	
	.order .item-center .left-l.right {
		
	}
	
	.order .item-center .left-l.right .name, .guest-address {
		font-weight: bold;
		padding-bottom: 10rpx;
	}
	.order .item-center .left-l.right .business-address {
		margin-bottom: 30rpx;
		font-size: 28rpx;
		color: #838383;
	}
	.order .item-bottom {
		font-weight: bold;
		margin-top: 30rpx;
	}
	.order .item-bottom button{
		border-radius: 80rpx;
	}
	/* --------------------------------------------------------------------弹出----------------------------------------- */
	.show {
		width: 100vw;
		height: 100vh;
		position: fixed;
		top: 0;
	}
	.show .bg {
		width: 100vw;
		height: 100vh;
		position: fixed;
		top: 0;
	}
	/* .show .bgc {
		width: 100%;
		height: 100%;
		position: fixed;
		top: 0;
	} */
	.show .show-item {
		display: inline-block;
		background-color: #4a505e;
		color: #FFFFFF;
		position: fixed;
		/* top: 96rpx; */
		/* top: 126rpx; */
		top: 180rpx;
		left: 284rpx;
		padding: 0 20rpx;
	}
	.show .show-item .item {
		border-bottom: 2rpx solid #808080;
		padding: 20rpx 15rpx;
		text-align: center;
	}
	.show .show-item .item .iconfont {
		font-size: 40rpx;
	}
	.show .show-item .item text {
		font-size: 28rpx;
	}
	.show .show-item .item .xiuxi {
		margin-left: 8rpx;
		margin-right: 13rpx;
	}
</style>
