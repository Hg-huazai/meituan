<template>
	<view>
		<view class="list">
			<navigator class="item" url="./wmdtj">
				<text class="iconfont icon-shuangsechangyongtubiao- left-l icon"></text>
				<text class="text left-l">外卖单统计</text>
				<text class="iconfont icon-youjiantou1 right-r"></text>
				<view class="clear">
					
				</view>
			</navigator>
			<navigator class="item" url="./ptdtj">
				<text class="iconfont icon-tongji3 left-l icon"></text>
				<text class="text left-l">跑腿单统计</text>
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
	.list {
		margin: 25rpx 0;
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
			.icon-youjiantou1 {
				font-size: 20rpx;
			}
		}
	}
</style>
