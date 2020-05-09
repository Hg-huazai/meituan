<template>
	<view class="content">
		<view class="list">
			<navigator class="item" url="./kfzt">
				<text class="text left-l">当前客服状态</text>
				<text class="iconfont icon-youjiantou1 right-r"></text>
				<text class="right-r">在线</text>
				<view class="clear">
					
				</view>
				<view class="all">
					此处为设置为配送员的客服状态
				</view>
			</navigator>
		</view>
		<view class="list">
			<navigator class="item" url="./mlzt">
				<text class="text left-l">忙碌状态自动回复</text>
				<text class="iconfont icon-youjiantou1 right-r"></text>
				<text class="right-r">暂未设置</text>
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
	.list {
		// margin-bottom: 25rpx;
		.item {
			margin: 25rpx 0;
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
			.iconfont {
				padding-top: 4rpx;
			}
			.all {
				margin-top: 20rpx;
				color: #b3b3b3;
			}
			.right-r {
				color: #b3b3b3;
			}
		}
	}
</style>
