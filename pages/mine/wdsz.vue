<template>
	<view>
		<view class="list">
			<navigator class="item" url="./xgmm">
				<text class="text left-l">修改密码</text>
				<text class="iconfont icon-youjiantou1 right-r"></text>
				<view class="clear">
					
				</view>
			</navigator>
		</view>
		<view class="button">
			<button type="">退出登录</button>
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
		margin: 30rpx 0;
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
			.iconfont {
				font-size: 28rpx;
			}
		}
	}
	.button {
		padding: 0 32rpx;
		button {
			background-color: #0ec3b4;
			color: #FFFFFF;
			font-size: 32rpx;
			padding: 10rpx 0;
		}
	}
</style>
