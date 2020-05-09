<template>
	<view class="content">
		<view class="menu">
			<view class="item" :class="[current == index ? 'active' : '']" v-for="(item, index) in menu" @click="menuclick(index)">
				{{item}}
			</view>
		</view>
		<view class="box" v-show="current == 0">
			<form @submit="zhanghu" @reset="">
				<view class="item">
					<text class="">银行</text>
					<text class="iconfont icon-youjiantou1 right-r"></text>
					<text class="right-r">
						<picker @change="bindPickerChange" :value="index" :range="array">
							<input type="text" :value="array[index]" placeholder="请选择开户银行" name="yinheng" disabled="true"/>
						</picker>
					</text>
					<view class="clear">
						
					</view>
					
				</view>
				<view class="item">
					<text class="">银行卡号</text>
					<text class="right-r"><input type="number" value="" placeholder="请输入银行卡号" name="number"/></text>
					<view class="clear">
						
					</view>
				</view>
				<view class="item">
					<text class="">开户人姓名</text>
					<text class="right-r"><input type="text" value="" placeholder="请输入开户人姓名" name="name"/></text>
					<view class="clear">
						
					</view>
				</view>
				
				<button form-type="submit">提交</button>
			</form>
		</view>
		<view class="box" v-show="current == 1">
			<form @submit="zfbzhanghu" @reset="">
				<view class="item">
					<text class="">支付宝账号</text>
					<text class="right-r"><input type="number" value="" placeholder="请输入支付宝账号" name="zfbnumber"/></text>
					<view class="clear">
						
					</view>
				</view>
				<view class="item">
					<text class="">支付宝姓名</text>
					<text class="right-r"><input type="text" value="" placeholder="请输入开户人姓名" name="zfbname"/></text>
					<view class="clear">
						
					</view>
				</view>
				
				<button form-type="submit">提交</button>
			</form>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				menu: ['提现到银行账号','提现到支付宝账户'],
				current: 0,
				array: [
					'工商银行', 
					'农业银行',
					'中国银行',
					'建设银行',
					'招商银行',
					'邮储银行',
					'交通银行',
					'浦发银行',
					'民生银行',
					'兴业银行',
					'平安银行',
					'中信银行',
					'华夏银行',
					'广发银行',
					'光大银行',
					'北京银行',
					'宁波银行',
				],
				index: 0,
			};
		},
		methods: {
			menuclick(e){
				this.current = e
			},
			// 获取from表单账号信息
			zhanghu(e) {
				console.log(e)
			},
			// 获取支付宝from表单账号信息
			zfbzhanghu(e) {
				console.log(e)
			},
			// 地区选择
			 bindPickerChange: function(e) {
			            console.log('picker发送选择改变，携带值为', e.target.value)
			            this.index = e.target.value
			        },
		}
	}
</script>

<style lang="less">
	page {
		background-color: #f5f5f5;
	}
	.menu {
		background-color: #fff;
		margin: 32rpx 64rpx;
		display: flex;
		font-size: 28rpx;
		border-radius: 40rpx;
		overflow: hidden;
		border: 1rpx solid #0ec3b4;
		
		.item {
			flex: 1;
			padding: 20rpx 0;
			text-align: center;
			color: #0ec3b4;
		}
		.active {
			background-color: #0ec3b4;
			color: #FFFFFF;
		}
	}
	.box {
		.item {
			font-size: 28rpx;
			padding: 32rpx;
			background-color: #FFFFFF;
			border-bottom: 1rpx solid #BABAC2;
			&:nth-last-child(1) {
				border-bottom: none;
			}
			text {
				display: inline-block;
				vertical-align: middle;
			}
			input {
				text-align: right;
				font-size: 28rpx;
			}
			.iconfont {
				font-size: 24rpx;
				margin-top: 8rpx;
				margin-left: 10rpx;
			}
		}
		button {
			margin: 32rpx;
			background-color: #0ec3b4;
			color: #FFFFFF;
		}
	}
</style>
