<template>
	<view class="denglu">
		<view class="login">
			<view class="name">
				快捷登录注册
			</view>
			<form @submit="formSubmit">
				<view class="phone">
					<text>+86</text>
					<text></text>
					<input type="number" name="phone" value="" placeholder="请输入手机号码"/>
				</view>
				<view class="yzm">
					<input type="number" name="yzm" value="" placeholder="请输入短信验证码"/>
					<button type="primary">获取验证码</button>
					<view class="clear">
					</view>
				</view>
				<view class="login-button">
					<button form-type="submit" @click="deluclick">登录</button>
				</view>
			</form>
		</view>
	</view>
</template>

<script>
	// var ab = /^[1][3,4,5,7,8][0-9]{9}$/;
	export default {
		methods: {
			formSubmit(e) {
				// console.log(e);
				console.log(e.detail.value.phone)
				console.log(e.detail.value.yzm)
				var phone = e.detail.value.phone
				var yzm = e.detail.value.yzm
				const type = uni.getStorageSync('type');
				
				var ab = /^[1][3,4,5,7,8][0-9]{9}$/;
				if (ab.test(phone) == false) {
					uni.showToast({
					    title: '手机号有误',
					    duration: 2000,
						icon:'none'
					});
				}else {
					if(!yzm) {
						// console.log('yzm1')
						uni.showToast({
						    title: '请输入验证码',
						    duration: 2000,
							icon:'none'
						});
					}else {
						getApp().globalData.phone=phone;
						uni.setStorage({
						    key: 'phone',
						    data: phone,
						    success: function () {
						        console.log('success');
						    }
						});
						uni.switchTab({
							url:"../index/index"
						})
					}
				}
			},
			deluclick(e){
				// console.log(e)
			}
		},
		onLoad() {
			// try {
			   
			// } catch (e) {
			//     // error
			// }
			
			// uni.getStorage({
			//     key: 'phone',
			//     success: function (res) {
			//         console.log(res);
			//     }
			// });
		}
	}
</script>

<style lang="less">
	.denglu {
		width: 100%;
	}
	.logo {
		width: 160rpx;
		height: 160rpx;
		background-color: #FEE3A5;
		border-radius: 50%;
		overflow: hidden;
		line-height: 160rpx;
		text-align: center;
		margin-top: 129rpx ;
		margin-left: 296rpx;
		font-size: 	36rpx;
		color: #444A49;
		font-weight: 600;
		image {
			width: 100%;
			height: 100%;
		}
	}
	.login {
		width: 100%;
		box-sizing: border-box;
		padding: 0 38rpx;
		
		.name {
			
			margin-top: 112rpx;
			font-size: 48rpx;
			color: #444A49;
		}
		form {
			.phone {
				margin-top: 30rpx;
				padding: 20rpx 0;
				box-sizing: border-box;
				border-bottom: 2rpx solid #979797;
				text:nth-child(1) {
					display: inline-block;
					vertical-align: middle;
					font-size: 32rpx;
					color: #444A49;
					padding-right: 24rpx;
				}
				text:nth-child(2){
					display: inline-block;
					vertical-align: middle;
					width: 2rpx;
					height: 24rpx;
					background-color: #979797;
					margin-right: 24rpx;
				}
				input {
					display: inline-block;
					vertical-align: middle;
					font-size: 30rpx;
				}
			}
			.yzm {
				padding: 10rpx 0;
				box-sizing: border-box;
				border-bottom: 2rpx solid #979797;
				input {
					display: inline-block;
					vertical-align: middle;
					color: #444A49;
					font-size: 30rpx;
					margin-top: 20rpx;
				}
				button {
					display: inline-block;
					vertical-align: middle;
					width: 184rpx;
					height: 84rpx;
					line-height: 84rpx;
					background-color: #C1B9B2;
					color: #FFFFFF;
					font-size: 26rpx;
					text-align: center;
					float: right;
				}
			}
			.login-button {
				margin-top: 92rpx;
				button {
					width: 672rpx;
					height: 96rpx;
					line-height: 96rpx;
					background-color: #0ec3b4;
					font-size: 32rpx;
				}
				
			}
		}
		
	}
	.bottom-tip {
		width: 100%;
		box-sizing: border-box;
		padding: 0 38rpx;
		color: #010101;
		margin-top: 382rpx;
		font-size: 22rpx;
		text:nth-child(2) {
			// font-size: 18rpx;
			border-bottom: 2rpx solid #000000;
		}
	}
</style>
