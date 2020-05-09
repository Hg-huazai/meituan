<template>
	<view class="content">
		<view class="title">
			店员客服状态
		</view>
		<form @submit="xiaoxi" @reset="">
			<radio-group @change="radioChange">
				<view class="item">
					<view class="left-l">
						在线
					</view>
					<view class="right-b">
						<laber key="yingyue">
							<radio name="在线" value="zaixian" style="transform:scale(0.7)" color="#0ec3b4" checked="true"/>
						</laber>
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="item">
					<view class="left-l">
						忙碌
					</view>
					<view class="right-b">
						<laber key="dingdan">
							<radio name="忙碌" value="manglv" style="transform:scale(0.7)" color="#0ec3b4"/>
						</laber>
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="item">
					<view class="left-l">
						离线	
					</view>
					<view class="right-b">
						<laber key="dingdan">
							<radio name="离线" value="lixian" style="transform:scale(0.7)" color="#0ec3b4"/>
						</laber>
					</view>
					<view class="clear">
						
					</view>
				</view>
			</radio-group>
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
		.item {
			padding: 25rpx 32rpx;
			border-bottom: 1rpx solid #dcdcdc;
			font-size: 28rpx;
			background-color: #FFFFFF;
			.right-r {
				background-color: #c5c5cb;
				border-radius: 5rpx;
				overflow: hidden;
				padding: 5rpx;
				font-size: 24rpx;
				text {
					display: inline-block;
					padding: 3rpx 8rpx;
					border-radius: 10rpx;
				}
				.active {
					background-color: #51CEB5;
					color: #FFFFFF;
				}
			}
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
