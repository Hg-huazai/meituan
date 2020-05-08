<template>
	<view class="content">
		<view class="top-info">
			<view class="active">
				<view class="img left-l">
					<image src="../../static/logo.png" mode=""></image>
				</view>
				<view class="info left-l">
					<view class="top">
						<text>#15176</text>
						<text>华华华</text>
					</view>
					<view class="bottom">
						<text>账户余额：</text>
						<text>¥ 180.0065</text>
					</view>
				</view>
				<view class="clear">
					
				</view>
			</view>
			<view class="bottom">
				<view class="item">
					<view class="text">
						今日外卖单
					</view>
					<view class="number">
						0
					</view>
				</view>
				<view class="item">
					<view class="text">
						今日跑腿单
					</view>
					<view class="number">
						0
					</view>
				</view>
				<view class="item">
					<view class="text">
						余额
					</view>
					<view class="number">
						¥180.00
					</view>
				</view>
			</view>
		</view>
		<!-- 我的账户 -->
		<view class="box">
			<view class="title">
				我的账户
			</view>
			<navigator class="item in-b" url="./zhmx">
				<view class="iconfont icon-wenben">
					
				</view>
				<view class="text">
					账户明细
				</view>
			</navigator>
			<navigator class="item in-b" url="./zc">
				<view class="iconfont icon-zichan1">
					
				</view>
				<view class="text">
					资产
				</view>
			</navigator>
			<navigator class="item in-b" url="./txjl">
				<view class="iconfont icon-jiedan">
					
				</view>
				<view class="text">
					提现记录
				</view>
			</navigator>
			<navigator class="item in-b" url="./wdsz">
				<view class="iconfont icon-shezhi">
					
				</view>
				<view class="text">
					我的设置
				</view>
			</navigator>
			<navigator class="item in-b" url="./wdpj">
				<view class="iconfont icon-xiaoxi">
					
				</view>
				<view class="text">
					我的评价
				</view>
			</navigator>
			<navigator class="item in-b" url="./yysz">
				<view class="iconfont icon-lingshengfan">
					
				</view>
				<view class="text">
					语音设置
				</view>
			</navigator>
			<navigator class="item in-b" url="./xxzx">
				<view class="iconfont icon-xiaoxi1">
					
				</view>
				<view class="text">
					消息中心
				</view>
			</navigator>
		</view>
		
		<!-- 统计-->
		<view class="box">
			<view class="title">
				统计
			</view>
			<navigator class="item in-b" url="./pstj">
				<view class="iconfont icon-tongji1">
					
				</view>
				<view class="text">
					配送统计
				</view>
			</navigator>
			<view class="item in-b">
				<view class="iconfont icon-tongji">
					
				</view>
				<view class="text">
					外卖排行
				</view>
			</view>
			<view class="item in-b">
				<view class="iconfont icon-shuangsechangyongtubiao-">
					
				</view>
				<view class="text">
					跑腿排行
				</view>
			</view>
			<view class="item in-b">
				<view class="iconfont icon-weizhi">
					
				</view>
				<view class="text">
					定位信息
				</view>
			</view>
			<navigator class="item in-b" url="./gglb">
				<view class="iconfont icon-wenben">
					
				</view>
				<view class="text">
					公告列表
				</view>
			</navigator>
			<view class="item in-b">
				<view class="iconfont icon-weizhi">
					
				</view>
				<view class="text">
					我的位置
				</view>
			</view>
		</view>
		<!-- tip -->
		<view class="tip">
			语由音技术由科大讯飞提供支持
		</view>
	</view>
</template>

<script>

	export default {
		
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
	
<style lang="less">
	
	.top-info {
		border-bottom: 20rpx solid #f5f5f5;
		padding: 32rpx;
		background-color: #0ec3b4;
		.active {
			padding-bottom: 40rpx;
			.img {
				width: 110rpx;
				height: 110rpx;
				border-radius: 50%;
				overflow: hidden;
				display: inline-block;
				vertical-align: middle;
				margin-right: 30rpx;
				image {
					width: 100%;
					height: 100%;
				}
			}
			.info {
				padding-top: 17rpx;
				display: inline-block;
				vertical-align: middle;
				color: #FFFFFF;
				font-size: 28rpx;
				text:nth-child(1){
					margin-right: 20rpx;
				}
			}
		}
		.bottom {
			display: flex;
			
			.item {
				flex: 1;
				text-align: center;color: #fff;
				font-size: 28rpx;
				border-right: 1rpx solid #FFFFFF;
				.number {
					margin-top: 10rpx;
				}
				&:nth-child(3){
					border-right: none;
				}
			}
		}
	}
	// 我的账号
	.box {
		border-bottom: 20rpx solid #f5f5f5;
		.title {
			font-size: 32rpx;
			border-bottom: 1rpx solid #f5f5f5;
			padding: 25rpx 32rpx;
		}
		.item {
			padding: 30rpx 0;
			font-size: 26rpx;
			width: 25%;
			text-align: center;
			color: #454545;
			.iconfont {
				font-size: 50rpx;
				margin-bottom: 10rpx;
			}
		}
	}
	.tip {
		background-color: #f5f5f5;
		padding:10rpx 0 30rpx 0;
		text-align: center;
		font-size: 28rpx;
		color: #9d9d9d;
	}
</style>