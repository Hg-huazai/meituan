<template>
	<view class="content">
		<view class="menu">
			<view class="item in-b" :class="[current == index ? 'active' : '']" v-for="(item,index) in menu" @click="menuclick(index)">
				{{item}}
			</view>
			<view class="box">
				<view class="item1 in-b" :class="[current1 == index ? 'active1' : '']" v-for="(item,index) in menu1" @click="menuclick1(index)">
					{{item}}
				</view>
			</view>
		</view>
		<view class="list">
			<!-- 第一名固定 -->
			<view class="title">
				<text>
					1
				</text>
				<text>
					<image src="../../static/logo.png" mode=""></image>
				</text>
				<text>华仔1</text>
				<text class="right-r">29%</text>
			</view>
			<!-- 排名列表 -->
				<!-- 第一名 -->
			<view class="item" v-for="(item ,index) in list">
				<text class="top">
					{{item.id}}
					<image v-if="item.id<4" src="../../static/images/paiming3.png" mode=""></image>
				</text>
				<text class="active">
					<image src="../../static/logo.png" mode=""></image>
				</text>
				<text>{{item.name}}</text>
				<text class="right-r">{{item.number}}%</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				menu: ['今日','昨日','本月','上月'],
				menu1: ['单量','准时率','平均时长'],
				current: 0,
				current1: 0,
				list: [
					{id: 1, name: '华仔1',number: 29},
					{id: 2, name: '华仔2',number: 24},
					{id: 3, name: '华仔3',number: 21},
					{id: 4, name: '华仔4',number: 16},
					{id: 5, name: '华仔5',number: 15},
					{id: 6, name: '华仔6',number: 9},
					{id: 7, name: '华仔7',number: 6},
					{id: 4, name: '华仔4',number: 16},
					{id: 5, name: '华仔5',number: 15},
					{id: 6, name: '华仔6',number: 9},
					{id: 7, name: '华仔7',number: 6},
				],
				one: [],
				
			};
		},
		onLoad() {
			// this.one = this.one.push(this.list[0])
			// console.log(this.one[0])
			// console.log(this.list[0])
		},
		methods: {
			menuclick(e){
				console.log(e)
				this.current = e;
				
			},
			menuclick1(e){
				console.log(e)
				this.current1 = e;
				
			}
		}
	}
</script>

<style lang="less">
	page {
		// background-color: #f5f5f5;
		
	}
	.content {
		padding-top: 200rpx;
	}
	.menu {
		// border-bottom: 1rpx solid #DCDCDC;
		background-color: #FFFFFF;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		z-index: 1;
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
		.active1 {
			background-color: #0ec3b4;
			color: #FFFFFF;
		}
		.box {
			margin: 20rpx 32rpx;
			border: 1rpx solid #0ec3b4;
			
			.item1 {
				box-sizing: border-box;
				width: 33.33%;
				text-align: center;
				font-size: 28rpx;
				padding:15rpx 0;
				border-right: 1rpx solid #0ec3b4;
				&:nth-last-child(1) {
					border-right: none;
				}
			}
		}
	}
	.list {
		padding: 0 32rpx;
		font-size: 28rpx;
		.title {
			padding: 20rpx 32rpx;
			padding-left: 0;
			background-color: #ececf4;
			border-radius: 100rpx;
			overflow: hidden;
			text {
				display: inline-block;
				vertical-align: middle;
				&:nth-child(1) {
					width: 20%;
					text-align: center;
					
				}
				&:nth-child(2) {
					margin-right: 20rpx;
				}
				&:nth-last-child(1) {
					padding-top: 20rpx;
				}
			}
			image {
				width: 80rpx;
				height: 80rpx;
				border-radius: 50%;
				overflow: hidden;
			}
		}
		.item {
			padding: 20rpx 32rpx;
			padding-left: 0;
			border-bottom: 1rpx solid #dadada;
			text {
				display: inline-block;
				vertical-align: middle;
				&:nth-child(1) {
					display: inline-block;
					width: 20%;
					text-align: center;
					position: relative;
				}
				&:nth-child(2) {
					margin-right: 20rpx;
				}
				&:nth-last-child(1) {
					padding-top: 20rpx;
				}
			}
			.active {
				image {
					width: 80rpx;
					height: 80rpx;
					border-radius: 50%;
					overflow: hidden;
				}
			}
			.top {
				
				image {
					position: absolute;
					top: -14rpx;
					left: 37rpx;
					width: 60rpx;
					height: 60rpx;
					z-index: -1;
				}
			}
		}
	}
</style>
