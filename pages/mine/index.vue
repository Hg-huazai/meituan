<template>
	<view class="content">
		<!-- ---------------------------------------------------自定义导航---------------------------------- -->
		<view class="example-body">
			<uni-nav-bar left-icon="arrowleft" right-text="菜单" left-text="返回" :title="title" @clickLeft="back" />
		</view>
		<view class="content1" v-bind:style="{'margin-top':topheight+'px'}">
			<view class="item">
				<view class="item1">
					<view class="left-l">
						<view class="iconfont icon-touxiang in-b"></view>
						<view class="user in-b">
							<view class="name">华哥 <i class="iconfont icon-youjiantou1"></i></view>
							<view class="level">
								<i class="iconfont icon-dengji"></i><text>普通等级</text>
							</view>
						</view>
					</view>
					<view class="right-r">
						<i class='iconfont icon-touxiang'></i>
						<view class="jibie">1级等峰</view>
					</view>
					<view class="clear"></view>
				</view>
				<view class="item2">
					<view class="box-item">
						<view class="number">
							0
						</view>
						<view class="">
							<text>今日完成订单</text><i class="iconfont icon-youjiantou1"></i>
						</view>
						<view class="null active in-b">
							排名: 暂无
						</view>
					</view>
					<view class="box-item">
						<view class="number">
							0.0
						</view>
						<view class="">
							<text>今日收入</text><i class="iconfont icon-youjiantou1"></i>
						</view>
						<view class="null">
							可提现收入: 0
						</view>
					</view>
					<view class="box-item">
						<view class="number">
							78
						</view>
						<view class="">
							<text>派单指数</text><i class="iconfont icon-youjiantou1"></i>
						</view>
						<view class="null">
							综合评价: 良
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="content2">
			<view class="item-top">
				奖励活动
			</view>
			<view class="item-bottom">
				<view class="top">
					<view class="item">
						<i class="iconfont icon-touxiang left-l"></i>
						<view class="yaoqing active left-l">红包活动</view>
					</view>
					<view class="item">
						<i class="iconfont icon-touxiang in-b"></i>
						<view class="hongbao in-b">
							<view class="yaoqing">
								邀请奖励
							</view>
							<view class="yaoqing1">
								邀请好友那168元
							</view>
						</view>
					</view>
				</view>
			</view>
			<!-- -------------------------------------------------------轮播图---------------------------------------------------->
			<view>
				<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" class="swiper" circular="true">
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/swper/images/swper_03.png" mode="widthFix"></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/swper/images/swper_03.png" mode="widthFix"></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/swper/images/swper_03.png" mode="widthFix"></image>
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<view class="content3">
			<view class="item-top">
				我的工具
			</view>
			<view class="item-bottom">
				<view class="item" v-for="item in icon" :key="index">
					<view class="iconfont" :class="item.icon"></view>
					<view class="text">
						{{item.name}}
					</view>
				</view>
			</view>
		</view>
		<view class="content4">
			<text>营业执照许可 <i class="iconfont icon-youjiantou"></i></text>
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
				title: '华哥',
				topheight: '',
				icon: [
					{name: "E骑士", icon: "icon-renzheng", state: 1},
					{name: "我的评价", icon: "icon-pingjia", state: 2},
					{name: "我的罚单", icon: "icon-chufadan", state: 3},
					{name: "接单检测", icon: "icon-jiance", state: 4},
					{name: "异常检测", icon: "icon-diannao", state: 5},
					{name: "蜂鸟商城", icon: "icon-shangcheng", state: 6},
					{name: "我的保险", icon: "icon-baoxian", state: 7},
					{name: "培训中心", icon: "icon-peixun", state: 8},
					{name: "骑士驿站", icon: "icon-yizhan", state: 9},
					{name: "金融服务", icon: "icon-jinrongfuwu", state: 10},
					{name: "我的客服", icon: "icon-icon-test", state: 11},
					{name: "奖惩规则", icon: "icon-wenben", state: 12},
					{name: "蓝色风暴", icon: "icon-fengbaochao", state: 13},
					{name: "拍店赚钱", icon: "icon-mo-03", state: 14},
					{name: "单量热力图", icon: "icon-tuceng", state: 15},
					{name: "骑士蜂卡", icon: "icon-qiapian", state: 16},
					
				]
			}
		},
		onLoad() {
			var view = uni.createSelectorQuery().select(".example-body");
			view.boundingClientRect(data => {
			console.log("节点离页面顶部的距离为" + data.height);
			// this.topheight = data.height;
			}).exec();
		},
		methods: {
			back() {
				uni.navigateBack({
					delta: 1
				})
			}
		}
	}
</script>
	
<style>
	.content {
		padding-top: 88rpx;
	}
	.example-body {
		padding-top: 30rpx;
		position: fixed;
		top: 0;
		z-index: 20;
	}
	.content1 {
		/* padding: 30rpx; */
		padding-top: 60rpx;
		background: -webkit-linear-gradient(top, #089eff, #f2f3f7);
	}
	.content1 .item {
		padding: 30rpx;
		background-color: #fff;
		border-radius: 60rpx;
	}
	.content1 .item .item1 .left-l  {
		margin-top: 30rpx;
	}
	.content1 .item .item1 .left-l .iconfont.in-b {
		font-size: 120rpx;
		color: #80ceff;
		vertical-align: middle;
	}
	.content1 .item .item1 .left-l .user {
		margin-left: 30rpx;
		vertical-align: middle;
	}
	.content1 .item .item1 .left-l .user .name {
		font-weight: bold;
		font-size: 40rpx;
	}
	.content1 .item .item1 .left-l .user .iconfont {
		font-size: 26rpx;
		font-weight: bold;
		color: #9c9c9c;
		margin-left: 10rpx;
	}
	.content1 .item .item1 .left-l .user .level {
		background-color: #80ceff;
		padding: 8rpx 20rpx;
		font-size: 24rpx;
		vertical-align: middle;
		position: relative;
		margin-top: 20rpx;
		padding-left: 40rpx;
		border-radius: 30rpx;
	}
	.content1 .item .item1 .left-l .user .level .iconfont {
		font-size: 60rpx;
		position: absolute;
		bottom: 0;
		left: -20rpx;
		color: #527fd0;
	}
	.content1 .item .item1 .right-r {
		position: relative;
	}
	.content1 .item .item1 .right-r .iconfont {
		font-size: 140rpx;
		color: #abf3ff;
	}
	.content1 .item .item1 .right-r .jibie {
		position: absolute;
		bottom: 0;
		left: -15%;
		background-color: #57c9ff;
		padding: 10rpx 20rpx;
		font-size: 10rpx;
		border-radius: 40rpx;
		width: 130%;
		box-sizing: border-box;
		text-align: center;
	}
	.content1 .item .item2 {
		display: flex;
	}
	.content1 .item .item2 .box-item {
		flex: 1;
		text-align: center;
		font-size: 22rpx;
		margin-top: 20rpx;
		color: #666666;
	}
	.content1 .item .item2 .box-item .number {
		font-weight: 500;
		font-size: 65rpx;
		color: #000;
	}
	.content1 .item .item2 .box-item .null {
		margin-top: 20rpx;
	}
	.content1 .item .item2 .box-item .null.active {
		margin-top: 20rpx;
		background-color: #f3f3f3;
		border-radius: 40rpx;
		padding: 5rpx 20rpx;
		font-size: 20rpx;
	}
	.content1 .item .item2 .box-item .iconfont {
		font-size: 20rpx;
	}
	.content2 {
		border-bottom: 20rpx solid #f2f3f7;
		/* margin-top: 88rpx; */
	}
	.content2 .item-top {
		color: #666666;
		font-size: 30rpx;
		font-weight: bold;
		padding: 20rpx;
		border-bottom: 2rpx solid #666666;
	}
	.content2 .item-bottom .top {
		display: flex;
		padding: 30rpx 0;
		font-size: 24rpx;
		margin: 0 30rpx;
		border-bottom: 2rpx solid #f5f5f5;
	}
	.content2 .item-bottom .top .iconfont{
		font-size: 120rpx;
		color: #6fdef9;
		margin-right: 20rpx;
	}
	.content2 .item-bottom .top .item{
		flex: 1;
	}
	.content2 .item-bottom .top .item .yaoqing{
		font-weight: bold;
		font-size: 40rpx;
		margin-bottom: 10rpx;
	}
	.content2 .item-bottom .top .item .yaoqing1{
		font-weight: bold;
		font-size: 20rpx;
		color: #a9a9a9;
	}
	.content2 .item-bottom .top .item .yaoqing.active{
		margin-top: 20rpx;
	}
	
	/* ----------------------------------------------------轮播图 */
	.swiper {
		height: 130rpx;
		margin: 20rpx 0;
	}
	.swiper-item {
		width: 100%;
		padding: 0 30rpx;
		box-sizing: border-box;
		height: 100%;
	}
	.swiper-item image{
		width: 100%;
	}
	.content3 .item-top {
		color: #666666;
		font-size: 30rpx;
		font-weight: bold;
		padding: 20rpx;
		border-bottom: 2rpx solid #666666;
	}
	.content3 .item-bottom {
		display: flex;
		flex-wrap: wrap;
		padding: 30rpx 0;
	}
	.content3 .item-bottom .item {
		width: 25%;
		text-align: center;
		margin-bottom: 20rpx;
	}
	.content3 .item-bottom .item .iconfont {
		font-size: 50rpx;
		color: #0d9bff;
		padding-bottom: 10rpx;
	}
	.content3 .item-bottom .item .text {
		font-size: 25rpx;
	}
	.content4 {
		background-color: #f2f3f7;
		text-align: center;
		padding: 30rpx 0;
		color: #089cfe;
		font-size: 28rpx;
	}
	.content4 .iconfont{
		font-size: 24rpx;
		margin-left: 15rpx;
	}
</style>