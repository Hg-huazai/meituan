<template>
	<view class="content">
		<view class="title">
			店员客服状态
		</view>
		<form @submit="xiaoxi" @reset="">
			<textarea value="" placeholder="当对话为忙碌状态时,将自动回复此内容给顾客" name="text"/>
			<view class="button">
				<button form-type="submit">保存修改</button>
			</view>
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods: {
			xiaoxi(e){
				console.log(e)
			},
			radioChange(e) {
				console.log(e)
			}
			
		}
	}
</script>

<style lang="less">
	page {
		background-color: #F5f5f5;
	}
	.right-b {
		float: right;
		radio {
			font-size: 30rpx;
			color: pink;
		}
	}
	.content {
		// padding: 32rpx;
		.title {
			font-size: 28rpx;
			padding: 25rpx 32rpx;
			color: #555555;
			
		}
		textarea {
			background-color: #fff;
			width: 100%;
			box-sizing: border-box;
			padding: 32rpx;
			font-size: 28rpx;
		}
		.button {
			margin-top: 30rpx;
			padding: 0 32rpx;
			button {
				background-color: #0ec3b4;
				color: #FFFFFF;
				font-size: 32rpx;
				padding: 10rpx 0;
			}
		}
	}
</style>
