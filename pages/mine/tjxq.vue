<template>
	<view class="content">
		<view class="list">
			<view class="box">
				<view class="item">
					日期
				</view>
				<view class="item">
					总收入
				</view>
				<view class="item">
					配送成功
				</view>
			</view>
			<view class="box" v-for="(item,index) in list">
				<view class="item">
					{{item.time}}
				</view>
				<view class="item">
					+￥{{item.money}}
				</view>
				<view class="item">
					{{item.succss}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					{time: '2020-05-09', money: '6', succss: '9'},
					{time: '2020-05-10', money: '6', succss: '9'},
					{time: '2020-05-11', money: '6', succss: '9'},
					{time: '2020-05-12', money: '6', succss: '9'},
					{time: '2020-05-13', money: '6', succss: '9'},
					{time: '2020-05-14', money: '6', succss: '9'},
					{time: '2020-05-15', money: '6', succss: '9'},
					{time: '2020-05-16', money: '6', succss: '9'}
				]
			};
		}
	}
</script>

<style lang="less">
	page {
		background-color: #f5f5f5;
	}
	.list{
		.box {
			display: flex;
			border-bottom: 1rpx solid #FFFFFF;
			
			.item {
				flex: 1;
				text-align: center;
				padding: 20rpx 0;
				font-size: 28rpx;
				border-right: 1rpx solid #FFFFFF;
				&:nth-child(2) {
					color: #0ec3b4;
				}
				&:nth-child(3) {
					border-right: none;
					color: #ff3352;
				}
			}
			&:nth-child(1) .item{
				color: #000000;
			}
			
			&:nth-child(2n-1) {
				background-color: #fff;
			}
			&:nth-child(1){
				background-color: #f5f5f5;
			}
		}
	}
</style>
