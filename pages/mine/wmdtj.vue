<template>
	<view class="content">
		<view class="menu">
			<view class="item in-b" :class="[current == index ? 'active' : '']" v-for="(item,index) in menu" @click="menuclick(index)">
				{{item}}
			</view>
		</view>
		<!-- 显示今天 -->
		<view class="list" v-show="current==0">
			<view class="item">
				<view class="top">
					<view class="left-l peisong">
						总收入
					</view>
					<view class="right-r money">
						￥50.00
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<view class="item">
				<view class="top">
					<view class="left-l peisong">
						配送成功
					</view>
					<view class="right-r money">
						10
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
		</view>
		<!-- 显示近7天 -->
		<view class="list" v-show="current==1">
			<view class="item">
				<view class="top">
					<view class="left-l peisong">
						总收入
					</view>
					<view class="right-r money">
						￥50.00
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<view class="item">
				<view class="top">
					<view class="left-l peisong">
						配送成功
					</view>
					<view class="right-r money">
						7
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<view class="button">
				<button type="">查看详情</button>
			</view>
		</view>
		<!-- 显示近30天 -->
		<view class="list" v-show="current==2">
			<view class="item">
				<view class="top">
					<view class="left-l peisong">
						总收入
					</view>
					<view class="right-r money">
						￥50.00
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<view class="item">
				<view class="top">
					<view class="left-l peisong">
						配送成功
					</view>
					<view class="right-r money">
						30
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<view class="button">
				<button type="">查看详情</button>
			</view>
		</view>
		<!-- 显示其他变动 -->
		<view class="list" v-show="current==3">
			<view class="item" >
				<view class="top">
					<view class="left-l peisong">
						总收入
					</view>
					<view class="right-r money">
						￥50.00
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<view class="item">
				<view class="top">
					<view class="left-l peisong">
						配送成功
					</view>
					<view class="right-r money">
						10
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<view class="button">
				<button type="">查看详情</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				menu: ['今天','近7天','近30天','自定义'],
				current: 0,
				list: [1,2,3,4],
				list1: []
			};
		},
		methods: {
			menuclick(e){
				console.log(e)
				this.current = e;
				
			}
		}
	}
</script>

<style lang="less">
	.content {
		
		padding-top: 93rpx;
	}
	page {
		background-color: #f5f5f5;
	}
	.menu {
		border-bottom: 1rpx solid #DCDCDC;
		background-color: #FFFFFF;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		.item {
			width: 25%;
			text-align: center;
			font-size: 28rpx;
			padding: 27rpx 0;
		}
		.active {
			color: #0ec3b4;
			border-bottom: 2rpx solid #0ec3b4;
		}
	}
	.list {
		.item {
			padding: 25rpx 32rpx;
			border-bottom: 1rpx solid #BABAC2;
			font-size: 28rpx;
			background-color: #FFFFFF;
			.top {
				.peisong {
					font-weight: 500;
					color: #333333;
				}
				.money{
					color: #0fc4b5;
				}
			}
			&:nth-child(2){
				border-bottom: none;
			}
		}
		
	}
	.button {
		padding: 0 32rpx;
		margin-top: 80rpx;
		button {
			background-color: #0ec3b4;
			color: #FFFFFF;
			font-size: 32rpx;
			padding: 10rpx 0;
		}
	}
</style>
