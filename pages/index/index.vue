<template>
	<view class="content">
		<view class="content1">
		
			<!-- -----------------------------------------状态-------------------------------------- -->
			<view class="state">
				<view class="uni-list kaigong">
					<view class="uni-list-cell uni-list-cell-pd">
						<view class="uni-list-cell-db left-l">接单状态</view>
						<switch checked class="right-r"  @change="switch1Change"/>
						<view class="clear">
							
						</view>
					</view>
				</view>
				<view class="box" v-if="kaigong">
					<view class="item" :class="[index === curren ? 'active' : '']" v-for="(item,index) in state" :key="index" @tap="statetap(index)">
						{{item.name}}
					</view>
				</view>
			</view>
			
		</view>
		
		
		
		<!-- ----------------------------------------------正文内容 ------------------------------------------------>
		<view class="content2" v-if="kaigong">
			<!-- 待抢单 -->
			
			<view class="content3">
				<!-- ----------------------------订单------------------------------ -->
				<navigator class="order" v-for="(item,index) in order" url="">
					<view class="item-top">
						<view class="left-l">
							<i class="iconfont icon-shijian"></i>
							<text>{{item.time}}分钟内送达</text>
						</view>
						<view class="right-r">
							￥<text>{{item.money}}</text>
						</view>
						<view class="clear"></view>
					</view>
					<view class="item-center">
						<view class="left-l left">
							<view class="business-distance">
								<!-- <text>0.5\n</text><text class="text2">km</text> -->
								<view class="text">{{item.newjili}}</view>
								<view class="text2">km</view>
							</view>
							
							<view class="iconfont icon-yuansu_juli"></view>
							
							<view class="guest-distance">
								<!-- <text>4.8\n</text><text class="text2">km</text> -->
								<view class="text">{{item.oldjili}}</view>
								<view class="text2">km</view>
							</view>
						</view>
						<view class="left-l right">
							<view class="name">{{item.name}}</view>
							<view class="business-address">{{item.newaddres}}</view>
							<view class="guest-address">{{item.oldaddres}}</view>
						</view>
						<view class="clear"></view>
					</view>
					<view class="item-bottom">
						<view  class="button" @click="qiandan(item.id)">
							<text v-if="item.state == 1">待抢单</text>
							<text v-if="item.state == 2">待取货</text>
							<text v-if="item.state == 3">待送达</text>
							<text v-if="item.state == 4">已完成</text>
						</view>
					</view>
				</navigator>
			</view>
			
			
		</view>
		
		
		<!-- ----------------------------------------------获得抢单资格---------------------------------------- -->
		<view class="float" v-if="kaigong" >
			获得抢单资格
		</view>
		<view class="null" v-if="!kaigong">
			<view class="icon">
				<text class="iconfont icon-fengbaochao"></text>
			</view>
			<view class="xx">
				您正在休息中
			</view>
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
					{name: "待送达",state: 3},
					{name: "已完成",state: 4}
				],
				list: [
					{time: '31', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号1', oldaddres: '中华国际中心B座(3601室)', money: 3, state: 1 ,id: '02'},
					{time: '23', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号1', oldaddres: '中华国际中心B座(3601室)', money: 5, state: 1 ,id: '04'},
					{time: '43', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号1', oldaddres: '中华国际中心B座(3601室)', money: 7, state: 1 ,id: '05'},
					{time: '24', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号2', oldaddres: '中华国际中心B座(3601室)', money: 8, state: 2 ,id: '119'},
					{time: '60', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号2', oldaddres: '中华国际中心B座(3601室)', money: 23, state: 2 ,id: '220'},
					{time: '34', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号3', oldaddres: '中华国际中心B座(3601室)', money: 42, state: 3 ,id: '230'},
					{time: '56', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号4', oldaddres: '中华国际中心B座(3601室)', money: 24, state: 4 ,id: '33'},
					{time: '23', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号4', oldaddres: '中华国际中心B座(3601室)', money: 54, state: 4 ,id: '66'},
					{time: '55', newjili: '0.5',oldjili: '4.8',name: '烧鹅王(体育西店)', newaddres: '广州市天河区体育西行街43号4', oldaddres: '中华国际中心B座(3601室)', money: 2, state: 4 ,id: '55'},
				],
				order:[],
				kaigong: true,
			}
		},
		onLoad() {
			var view = uni.createSelectorQuery().select(".content1");
			view.boundingClientRect(data => {
			console.log("节点离页面顶部的距离为" + data.height);
			this.topheight = data.height
			}).exec();
			
			// 首次进入显示待抢单
			var list1 = this.list.filter(res => res.state == 1);
			this.order = list1
			
		},
		methods: {
			statetap(e) {
				this.curren = e ;
				// var list1=[]
				var list1 = this.list.filter(res => res.state == e+1);
				this.order = list1
				
			},
			// 点击抢单
			qiandan(e){
				uni.navigateTo({
					url:'../details/details?id='+e
				})
			},
			onClickbg (){
				this.show = 'none',
				this.icon = 'icon-jiantou'
			},
		}
	}
</script>

<style lang="less">
	page {
		background-color: #F8F8F8;
	}
	.null {
		text-align: center;
		margin-top: 100rpx;
		.icon {
			width: 300rpx;
			height: 300rpx;
			line-height: 300rpx;
			text-align: center;
			background-color: #FFFFFF;
			margin: 0 auto;
			border-radius: 50%;
			overflow: hidden;
			.iconfont {
				font-size: 120rpx;
			}
		}
		.xx {
			margin-top: 30rpx;
			font-size: 30rpx;
		}
	}
	.kaigong {
		width: 100%;
		margin-bottom: 20rpx;
	}
	.content {
		padding-top: 184rpx;
	}
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
		/* box-sizing: border-box; */
		/* justify-content: space-between; */
		/* background: -webkit-linear-gradient(top,#a3a3a3,#21232f); */
		align-items: flex-start;
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
		bottom: 25px;
	}
	.content1-top .item {
		flex: 1;
		/* width: 33%; */
		/* background-color: pink; */
		/* border: 2rpx solid red; */
		white-space: nowrap !important;
	}
	.content1-top .item.center {
		text-align: center;
		/* background-color: pink; */
	}
	.content1-top .item .work {
		font-weight: bold;
		/* background-color: blue; */
	}
	.content1-top .item.center .iconfont {
		/* background-color: red; */
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
		position: fixed;
		top: 0;
		width: 100%;
		color: #fff;
		background-color: #0ec3b4;
		box-sizing: border-box;
		z-index: 4;
	}
	.state .box {
		display: flex;
		/* width: 100%; */
		font-size: 32rpx;
		color: #FFFFFF;
		z-index: 4;
		
	}
	.state .box .active{
		border-bottom: 8rpx solid #fff;
	}
	.state .box .item{
		padding-bottom: 10rpx;
		flex: 1;
		text-align: center;
		
	}
	.state .box .iconfont{
		font-size: 26rpx;
		margin-left: 20rpx;
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
	.order .item-bottom .button{
		border-radius: 80rpx;
		padding: 20rpx;
		font-size: 32rpx;
		color: #fff;
		text-align: center;
		background-color: #0ec3b4;
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
