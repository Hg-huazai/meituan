<template>
	<view class="content1">
		<view class="content1-top">
			<view class="item">
				<navigator class="iconfont icon-youjiantou1-copy"  open-type="navigateBack"></navigator>
			</view>
			<view class="item center" @click="onClickshow">
				<text class="work">
					消息中心-【在线】
				</text>
				<!-- <i class="iconfont" :class="icon"></i> -->
			</view>
			<navigator class="item right" url="./gkxxsz">
				<i class="iconfont icon-shezhi"></i>
			</navigator>
			
		</view>
	</view>
</template>

<script>
	import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
	export default {
		components: {
			uniNavBar
		},
		data() {
			return {
				
			};
		},
		methods: {
			
		}
	}
</script>

<style lang="less">
	
	.content1 {
		position: fixed;
		top: 0;
		width: 100%;
	}
	.content1-top {
		/* margin-top: 30rpx; */
		padding:50rpx 20rpx 30rpx;
		/* border-top: 35rpx solid #a1a1a1; */
		/* padding: 20rpx; */
		display: flex;
		color: #fff;
		background-color: #0ec3b4;
		/* box-sizing: border-box; */
		/* justify-content: space-between; */
		/* background: -webkit-linear-gradient(top,#a3a3a3,#21232f); */
		align-items: flex-start;
	}
	.content1-top .iconfont {
		font-size: 50rpx;
		color: #fff;
	}
	.content1-top .iconfont.icon-jiantou{
		font-size: 30rpx;
		margin-left: 15rpx;
	}
	.content1-top .iconfont.icon-jiantou-copy{
		font-size: 30rpx;
		margin-left: 15rpx;
		bottom: 25px;
	}
	.content1-top .item {
		flex: 1;
		/* width: 33%; */
		/* background-color: pink; */
		/* border: 2rpx solid red; */
		white-space: nowrap !important;
	}
	.content1-top .item.center {
		text-align: center;
		/* background-color: pink; */
	}
	.content1-top .item .work {
		font-weight: bold;
		/* background-color: blue; */
	}
	.content1-top .item.center .iconfont {
		/* background-color: red; */
	}
	.content1-top .item.right .iconfont {
		float: right;
		
	}
</style>
