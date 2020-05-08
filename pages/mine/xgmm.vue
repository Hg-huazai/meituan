<template>
	<view>
		<form @submit="xiugai" @reset="">
			<view class="list">
				<view class="item">
					<input type="number" value="" placeholder="当前密码" />
				</view>
				<view class="item">
					<input type="number" value="" placeholder="新密码" />
				</view>
				<view class="item">
					<input type="number" value="" placeholder="确认新密码" />
				</view>
			</view>
			<view class="button">
				<button type="" form-type="submit">退出登录</button>
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
			// 获取表单数据
			xiugai(e){
				console.log(e)
			}
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
			input {
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
