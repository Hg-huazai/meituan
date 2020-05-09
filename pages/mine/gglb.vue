<template>
	<view>
		<view class="null">
			<view class="box">
				<text class="iconfont icon-jiedan"></text>
			</view>
			<view class="text">
				暂无数据！
			</view>
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
	.null {
		// background-color: #f5f5f5;
		// height: 100vh;
		.box {
			
			width: 250rpx;
			height: 250rpx;
			text-align: center;
			line-height: 250rpx;
			border-radius: 50%;
			overflow: hidden;
			background-color: #FFFFFF;
			margin: 0 auto;
			margin-top: 300rpx;
			.iconfont {
				font-size: 120rpx;
				color: #e5e5e5;
				font-weight: 600;
			}
		}
		.text {
			margin-top: 40rpx;
			text-align: center;
			color: #84929d;
			font-size: 28rpx;
		}
	}
</style>
