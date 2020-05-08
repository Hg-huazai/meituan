<template>
	<view class="content">
		<view class="title">
			语音提示
		</view>
		<view class="item">
			<view class="left-l">
				微信模板消息提醒
			</view>
			<view class="right-r" @click="xianjiclick">
				<text :class="{active: xianji == 1}">on</text>
				<text :class="{active: xianji == 0}">off</text>
			</view>
			<view class="clear">
				
			</view>
		</view>
		<view class="item">
			<view class="left-l">
				语音电话提醒
			</view>
			<view class="right-r" @click="xianceclick">
				<text :class="{active: xiance == 1}">on</text>
				<text :class="{active: xiance == 0}">off</text>
			</view>
			<view class="clear">
				
			</view>
		</view>
		<view class="item">
			<view class="left-l">
				语音提示
			</view>
			<view class="right-r" @click="yuyingclick">
				<text :class="{active: yuying == 1}">on</text>
				<text :class="{active: yuying == 0}">off</text>
			</view>
			<view class="clear">
				
			</view>
		</view>
		<view class="item">
			<view class="left-l">
				新消息震动
			</view>
			<view class="right-r" @click="xinxiaoxiclick">
				<text :class="{active: xinxiaoxi == 1}">on</text>
				<text :class="{active: xinxiaoxi == 0}">off</text>
			</view>
			<view class="clear">
				
			</view>
		</view>
		<view class="title">
			铃声
		</view>
		<radio-group @change="radioChange">	
			<view class="item">
				<view class="left-l">
					音乐
				</view>
				<view class="right-b">
					<laber key="yingyue">
						<radio value="yingyue" style="transform:scale(0.7)" />
					</laber>
				</view>
				<view class="clear">
					
				</view>
			</view>
			<view class="item">
				<view class="left-l">
					订单内容
				</view>
				<view class="right-b">
					<laber key="dingdan">
						<radio value="dingdan" style="transform:scale(0.7)"/>
					</laber>
				</view>
				<view class="clear">
					
				</view>
			</view>
		</radio-group>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				xianji: 1,
				xiance: 0,
				yuying: 1,
				xinxiaoxi: 0,
			};
		},
		methods: {
			// 微信模板消息授权
			xianjiclick(){
				if(this.xianji==1) {
					this.xianji=0
					console.log('微信模板消息不授权')
				}else{
					this.xianji=1
					console.log('微信模板消息授权')
				}
			},
			// 语音电话提醒授权
			xianceclick(){
				if(this.xiance==1) {
					this.xiance=0
					console.log('语音电话提醒不授权')
				}else{
					this.xiance=1
					console.log('语音电话提醒授权')
				}
			},
			// 语音提示授权
			yuyingclick(){
				if(this.yuying==1) {
					this.yuying=0
					console.log('语音提示不授权')
				}else{
					this.yuying=1
					console.log('语音提示授权')
				}
			},
			// 新消息震动
			xinxiaoxiclick(){
				if(this.xinxiaoxi==1) {
					this.xinxiaoxi=0
					console.log('新消息震动不授权')
				}else{
					this.xinxiaoxi=1
					console.log('新消息震动授权')
				}
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
			padding: 25rpx 32rpx;
			
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
	}
</style>
