<template>
	<view class="content">
		<view class="menu">
			<view class="item in-b" :class="[current == index ? 'active' : '']" v-for="(item,index) in menu" @click="menuclick(index)">
				{{item}}
			</view>
		</view>
		<!-- 显示全部 -->
		<view class="list" v-show="current==0">
			<view class="item" v-for="(item, index) in list">
				<view class="top">
					<view class="left-l peisong">
						配送费入账
					</view>
					<view class="right-r money">
						+5.00
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="bottom">
					<view class="left-l time">
						<text>2020-05-05</text>
						<text>17:05</text>
					</view>
					<view class="right-r money">
						<text>余额：</text>
						<text>¥180.00</text>
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<!-- 数据为空是显示 -->
			<view class="null" v-if="list.length == 0">
				<view class="box">
					<text class="iconfont icon-jiedan"></text>
				</view>
				<view class="text">
					没有符合条件的数据！
				</view>
			</view>
		</view>
		<!-- 显示配送费入账 -->
		<view class="list" v-show="current==1">
			<view class="item" v-for="(item, index) in list">
				<view class="top">
					<view class="left-l peisong">
						配送费入账
					</view>
					<view class="right-r money">
						+5.00
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="bottom">
					<view class="left-l time">
						<text>2020-05-05</text>
						<text>17:05</text>
					</view>
					<view class="right-r money">
						<text>余额：</text>
						<text>¥180.00</text>
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<!-- 数据为空是显示 -->
			<view class="null" v-if="list.length == 0">
				<view class="box">
					<text class="iconfont icon-jiedan"></text>
				</view>
				<view class="text">
					没有符合条件的数据！
				</view>
			</view>
		</view>
		<!-- 显示申请变动 -->
		<view class="list" v-show="current==2">
			<view class="item" v-for="(item, index) in list1">
				<view class="top">
					<view class="left-l peisong">
						配送费入账
					</view>
					<view class="right-r money">
						+5.00
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="bottom">
					<view class="left-l time">
						<text>2020-05-05</text>
						<text>17:05</text>
					</view>
					<view class="right-r money">
						<text>余额：</text>
						<text>¥180.00</text>
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<!-- 数据为空是显示 -->
			<view class="null" v-if="list1.length == 0">
				<view class="box">
					<text class="iconfont icon-jiedan"></text>
				</view>
				<view class="text">
					没有符合条件的数据！
				</view>
			</view>
		</view>
		<!-- 显示其他变动 -->
		<view class="list" v-show="current==3">
			<view class="item" v-for="(item, index) in list1">
				<view class="top">
					<view class="left-l peisong">
						配送费入账
					</view>
					<view class="right-r money">
						+5.00
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="bottom">
					<view class="left-l time">
						<text>2020-05-05</text>
						<text>17:05</text>
					</view>
					<view class="right-r money">
						<text>余额：</text>
						<text>¥180.00</text>
					</view>
					<view class="clear">
						
					</view>
				</view>
			</view>
			<view class="null" v-if="list1.length == 0">
				<view class="box">
					<text class="iconfont icon-jiedan"></text>
				</view>
				<view class="text">
					没有符合条件的数据！
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				menu: ['全部','申请中','提现成功','撤销'],
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
			.top {
				.peisong {
					font-weight: 500;
					color: #333333;
				}
				.money{
					color: #0fc4b5;
				}
			}
			.bottom {
				margin-top: 10rpx;
				color: #9b9b9b;
			}
		}
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
