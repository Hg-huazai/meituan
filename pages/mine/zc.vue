<template>
	<view>
		<view class="top">
			<view class="text">
				账户可用余额(元)
			</view>
			<view class="money">
				￥180.00
			</view>
		</view>
		<view class="list">
			<navigator class="item" url="./zhmx">
				<text class="iconfont icon-gerenzhongxin_xuanzhong-copy left-l icon"></text>
				<text class="text left-l">账户明细</text>
				<text class="iconfont icon-youjiantou1 right-r"></text>
				<view class="clear">
					
				</view>
			</navigator>
			<navigator class="item" url="./txjl">
				<text class="iconfont icon-wenben left-l icon"></text>
				<text class="text left-l">提现记录</text>
				<text class="iconfont icon-youjiantou1 right-r"></text>
				<view class="clear">
					
				</view>
			</navigator>
		</view>
		<view class="list">
			<navigator class="item" url="./sqtx">
				<text class="iconfont icon-jinrongfuwu left-l icon"></text>
				<text class="text left-l">申请提现</text>
				<text class="iconfont icon-youjiantou1 right-r"></text>
				<view class="clear">
					
				</view>
			</navigator>
		</view>
		
		<view class="list">
			<navigator class="item" url="./txzh">
				<text class="iconfont icon-qiapian left-l icon"></text>
				<text class="text left-l">提现账户</text>
				<text class="iconfont icon-youjiantou1 right-r"></text>
				<view class="clear">
					
				</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="less">
	page {
		background-color: #f5f5f5;
	}
	.top {
		padding: 80rpx 0 100rpx 0;
		background-color: #0ec3b4;
		color: #FFFFFF;
		font-size: 28rpx;
		margin-bottom: 25rpx;
		.text {
			text-align: center;
		}
		.money {
			margin-top: 30rpx;
			text-align: center;
			font-size: 40rpx;
			font-weight: 600;
		}
	}
	.list {
		margin-bottom: 25rpx;
		.item {
			background-color: #FFFFFF;
			padding: 30rpx 20rpx;
			border-bottom: 1rpx solid #D3D3D3;
			font-size: 28rpx;
			&:nth-last-child(1) {
				border-bottom: none;
			}
			text {
				display: inline-block;
				vertical-align: middle;
				
			}
			.icon {
				color: #0ec3b4;
				margin-right: 20rpx;
			}
		}
	}
</style>
