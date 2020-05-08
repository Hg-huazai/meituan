<template>
	<view class="content">
		<view class="menu">
			<view class="item in-b" :class="[current == index ? 'active' : '']" v-for="(item,index) in menu" @click="menuclick(index)">
				{{item}}
			</view>
		</view>
		<!-- 显示全部 -->
		<view class="list" v-show="current==0" >
			<view class="title" v-if="list.length != 0">
				<text>总评分</text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text>5分</text>
			</view>
			<view class="item" v-for="(item, index) in list">
				<view class="top">
					<view class="left-l time">
						<text>顾客评价</text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
					</view>
					<view class="right-r money">
						<text>2020-04-05</text>
						<text>08：59</text>
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="bottom">
					评价内容评价内容评价内容
				</view>
			</view>
			<view class="nullall" v-if="list.length != 0">
				没有更多了
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
		<!-- 显示满意 -->
		<view class="list" v-show="current==1" >
			<view class="title" v-if="list.length != 0">
				<text>总评分</text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text>5分</text>
			</view>
			<view class="item" v-for="(item, index) in list">
				<view class="top">
					<view class="left-l time">
						<text>顾客评价</text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
					</view>
					<view class="right-r money">
						<text>2020-04-05</text>
						<text>08：59</text>
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="bottom">
					评价内容评价内容评价内容
				</view>
			</view>
			<view class="nullall" v-if="list.length != 0">
				没有更多了
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
		<!-- 显示不满意 -->
		<view class="list" v-show="current==2" >
			<view class="title" v-if="list1.length != 0">
				<text>总评分</text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text class="iconfont icon-xing1"></text>
				<text>5分</text>
			</view>
			<view class="item" v-for="(item, index) in list1">
				<view class="top">
					<view class="left-l time">
						<text>顾客评价</text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
						<text class="iconfont icon-xing1"></text>
					</view>
					<view class="right-r money">
						<text>2020-04-05</text>
						<text>08：59</text>
					</view>
					<view class="clear">
						
					</view>
				</view>
				<view class="bottom">
					评价内容评价内容评价内容
				</view>
			</view>
			<view class="nullall" v-if="list1.length != 0">
				没有更多了
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
	</view>
</template>

<script>
	export default {
		data() {
			return {
				menu: ['全部','满意','不满意'],
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
			width: 33.33%;
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
		.title {
			font-size: 28rpx;
			margin-left: 32rpx;
			padding: 30rpx 0;
			.iconfont {
				color: #FF9600;
				font-size: 20rpx;
				margin-right: 5rpx;
			}
			text:nth-child(1) {
				color: #0fc4b5;
				margin-right: 20rpx;
			}
			text:nth-last-child(1){
				margin-left: 20rpx;
				font-size: 24rpx;
				color: #838383;
			}
			
		}
		.item {
			background-color: #fff;
			padding: 25rpx 32rpx;
			border-bottom: 1rpx solid #BABAC2;
			font-size: 28rpx;
			
			.top {
				margin-top: 10rpx;
				color: #9b9b9b;
				.time {
					text:nth-child(1) {
						margin-right: 20rpx;
					}
					.iconfont {
						color: #FF9600;
						font-size: 20rpx;
						margin-right: 5rpx;
					}
				}
				.money {
					text:nth-child(1){
						margin-right: 20rpx;
					}
				}
			}
			.bottom {
				margin-top: 10rpx;
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
	.nullall {
		font-size: 28rpx;
		text-align: center;
		padding: 40rpx 0;
		color: #838383;
	}
</style>
