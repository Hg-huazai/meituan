<template>
	<view class="content">
		<view class="title">
			<text>账号可用余额 :</text>
			<text>￥180.00</text>
		</view>
		
		<form @submit="frommoney" @reset="">
			<view class="box">
				<view class="title1">
					提现金额
				</view>
				<view class="input">
					<input type="number" value=""  placeholder="请输入提现金额" name="money"/>
				</view>
				<view class="money">
					<text class="dian"></text>
					<text>最低提现金额为100</text>
				</view>
				<view class="money">
					<text class="dian"></text>
					<text>提现费率为1%，最低收取1元，最高收取一元</text>
				</view>
				<view class="title1">
					提现方式
				</view>
			</view>
			<radio-group @change="radioChange">	
			<laber key="yingyue" v-for="(item,index) in list" :for="item.name">
				<view class="item">
					<view class="left-l">
						{{item.value}}
					</view>
					<view class="right-b">
						
							<radio value="yingyue" style="transform:scale(0.7)" :id="item.name" :value="item.name" color="#0ec3b4" :checked="item.checked"/>
						
					</view>
					<view class="clear">
						
					</view>
				</view>
				</laber>
				<!-- <view class="item">
					<view class="left-l">
						支付宝提现
					</view>
					<view class="right-b">
						<laber key="yingyue">
							<radio value="yingyue" style="transform:scale(0.7)" color="#0ec3b4"/>
						</laber>
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="item">
					<view class="left-l">
						银行卡提现
					</view>
					<view class="right-b">
						<laber key="dingdan">
							<radio value="dingdan" style="transform:scale(0.7)" color="#0ec3b4"/>
						</laber>
					</view>
					<view class="clear">
						
					</view>
				</view> -->
			</radio-group>
				
			<button form-type="submit">提现</button>
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					{name: 'wx',value: '微信提现',checked: true},
					{name: 'zfb',value: '支付宝提现'},
					{name: 'yhk',value: '银行卡提现'},
				]
			};
		},
		methods: {
			// 表单获取提现金额
			frommoney(e){
				console.log(e.detail.value.money)
			},
			radioChange(e){
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
			padding: 30rpx 32rpx;
			background-color: #fff;
			margin: 20rpx 0;
			color: #989898;
			text:nth-child(2){
				margin-left: 20rpx;
				color: #0ec3b4;
			}
		}
		.item {
			color: #989898;
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
	}
	.box {
		background-color: #FFFFFF;
		font-size: 28rpx;
		color: #989898;
		padding:0 32rpx;
		padding-bottom: 0;
		.title1 {
			color: #000;
			padding-top: 32rpx;
		}
		.input {
			margin: 25rpx 0;
			input {
				border: 1rpx solid #989898;
				padding: 20rpx;
				font-size: 28rpx;
				border-radius: 10rpx;
			}
		}
		.money {
			text {
				display: inline-block;
				vertical-align: middle;
			}
			.dian {
				display: inline-block;
				height: 15rpx;
				width: 15rpx;
				border-radius: 50%;
				overflow: hidden;
				background-color: #989898;
				margin-right: 20rpx;
			}
			&:nth-last-child(1) {
				margin-bottom: 20rpx;
			}
		}
	}
	button {
		color: #fff;
		background-color: #0ec3b4;
		margin: 32rpx;
	}
</style>
