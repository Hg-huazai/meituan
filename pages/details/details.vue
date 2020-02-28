<template>
	<view class="content">
		<!-- --------------------------------------------------------自定义头部 -------------------------------->
		<view class="example-body">
			<uni-nav-bar left-icon="arrowleft" right-text="" left-text="" title="订单详情" @clickLeft="back" />
		</view>
		<!-- ----------------------------------------------------------地图 ----------------------------------------->
		<view class="map">
			<map></map>
		</view>
		
		
		<!-- --------------------------------------------------------------底部固定-------------------------------------- -->
		<view class="content-bottom">
			<button type="primary">抢单</button>
		</view>
		
		<!-- --------------------------------------------------------------详情 ------------------------------------------------>
		<view class="details">
			<view class="box-xiahuaxian">
				<view class="item"></view>
			</view>
			<view class="number">
				<view class="left-l">
					<icon class="iconfont icon-shijian"></icon>
					<text>18:20~18:40送达</text>
				</view>
				<view class="right-r">
					￥<text>7.2</text>
				</view>
				<view class="clear"></view>
			</view>
			<view class="info">
				<view class="item1">
					<view class="left-l left">
						<view class="left">取</view>
					</view>
					<view class="left-l right">开心花甲粉(花城汇店)</view>
					<view class="clear"></view>
				</view>
				<view class="item2">
					<view class="in-b left">
						<view class="left-item1">2.5</view>
						<view class="left-item2">km</view>
					</view>
					<view class="in-b right">广州市天河区体育西行街43号花城汇负一层北区C区</view>
					<view class="clear"></view>
				</view>
				<view class="item1">
					<view class="left-l left" >
						<view class="left" style="background-color: #43d100;">送</view>
					</view>
					<view class="left-l right ">娇林菀(娇林街61号A栋隔壁幸福驿站的村口美宜佳)</view>
					<view class="clear"></view>
				</view>
			</view>
			<!-- -----------------------要求----------------------------- -->
			<view class="requirement">
				<view class="top">
					<view class="left-l">特殊要求</view>
					<view class="right-r"></view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">顾客备注</view>
					<view class="right-r">1份餐具</view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">发票</view>
					<view class="right-r">不需要</view>
					<view class="clear"></view>
				</view>
			</view>
			
			<!-- -----------------------餐品----------------------------- -->
			<view class="requirement">
				<view class="top">
					<view class="left-l">餐品<text>(总价 ￥17.5)</text></view>
					<view class="right-r">x3</view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">免费加粉丝(限一份)</view>
					<view class="right-r">x1</view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">肥牛</view>
					<view class="right-r">x1</view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">鲜虾+肥牛+花甲粉</view>
					<view class="right-r">x1</view>
					<view class="clear"></view>
				</view>
			</view>
			
			<!-- -----------------------订单信息------------------------- -->
			<view class="requirement">
				<view class="top">
					<view class="left-l">订单信息</view>
					<view class="right-r"></view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">订单号</view>
					<view class="right-r">3000145120109406807 <text class="copy">复制</text></view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">订单类型</view>
					<view class="right-r">外卖</view>
					<view class="clear"></view>
				</view>
			</view>
			
			<!-- -----------------------配送------------------------- -->
			<view class="requirement">
				<view class="peisong">
					<view class="dian ">
						<i class="iconfont icon-yuandian"></i>
						<text></text>
						<i class="iconfont icon-yuandian"></i>
						<text></text>
						<i class="iconfont icon-yuandian"></i>
						<text></text>
						<i class="iconfont icon-yuandian"></i>
					</view>
					<view class="xinxi">
						<view class="box">
							<view class="box-item">接单时间</view>
						</view>
						<view class="box">
							<view class="box-item">实际到店</view>
						</view>
						<view class="box">
							<view class="box-item">实际取餐</view>
						</view>
						<view class="box">
							<view class="box-item">实际送达</view>
						</view>
					</view>
				</view>
			</view>
			
			<!-- -----------------------收入明细----------------------------- -->
			<view class="requirement">
				<view class="top">
					<view class="left-l">收入明细</view>
					<view class="right-r"></view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">基础配送费</view>
					<view class="right-r">￥5.6</view>
					<view class="clear"></view>
				</view>
				<view class="item">
					<view class="left-l">特殊简历</view>
					<view class="right-r">￥1.6</view>
					<view class="clear"></view>
				</view>
			</view>
		</view>
		
		
	</view>
	
</template>

<script>
	import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
	export default {
		components: {
			uniNavBar
		},
		data(){
			return {
				
			}
		},
		onLoad (){
			
		},
		methods: {
			back() {
				uni.navigateBack({
					delta: 1
				})
			}
		}
	}
</script>

<style>
	.example-body {
		position: fixed;
		top: 0;
		z-index: 3;
	}
	/* ----------------------------------------------------------------------地图 */
	.map map {
		width: 100%;
		height: 800rpx;
	}
	
	/* ----------------------------------------------------------------------详情 */
	.details {
		margin-bottom: 134rpx;
	}
	.details .box-xiahuaxian {
		width: 100%;
		text-align: center;
		/* margin-top: 5rpx; */
	}
	.details .box-xiahuaxian .item {
		width: 80rpx;
		height: 10rpx;
		background-color: #d8d8d8;
		border-radius: 30rpx;
		display: inline-block;
	}
	
	.details .number {
		padding: 20rpx;
	}
	.details .number .left-l {
		/* width: 10%; */
	}
	.details .number .left-l .iconfont{
		margin-right: 20rpx;
		color: #999999;
		font-size: 38rpx;
	}
	.details .number .left-l text {
		font-weight: bold;
		font-size: 38rpx;
	}
	.details .number .right-r {
		color: #f2590d;
		font-weight: bold;
		font-size: 25rpx;
	}
	.details .number .right-r text {
		
		font-size: 40rpx;
	}
	
	.details .info {
		padding: 20rpx;
		border-bottom: 20rpx solid #ededf5;
	}
	.details .info .left-l.left {
		width: 10%;
		text-align: center;
	}
	.details .info .left-l.right {
		width: 87%;
		margin-left: 3%;
	}
	.details .info .left-l .left {
		/* width: 10%; */
		width: 40rpx;
		height: 40rpx;
		line-height: 40rpx;
		background-color: #009bff;
		text-align: center;
		display: inline-block;
		border-radius: 50%;
		font-size: 8rpx;
		color: #FFFFFF;
	}
	
	.details .info .left-l.right {
		font-weight: bold;
		font-size: 37rpx;
	}
	.details .info .item2 .left {
		width: 10%;
		text-align: center;
	}
	.details .info .item2 .left .left-item1 {
		font-weight: bold;
		font-size: 25rpx;
	}
	.details .info .item2 .left .left-item2 {
		color: #666666;
		font-size: 20rpx;
	}
	.details .info .item2 .right {
		font-weight: normal;
		color: #666666;
		font-size: 28rpx;
		margin-top: 10rpx;
		margin-bottom: 20rpx;
		width: 82%;
		margin-left: 3%;
	}
	/* --------------------------------详情特殊要求 */
	.details .requirement {
		border-bottom: 20rpx solid #ededf5;
	}
	.details .requirement .top {
		padding: 20rpx;
		border-bottom: 2rpx solid #ededf5;
	}
	.details .requirement .top .left-l {
		font-size: 34rpx;
		font-weight: bold;
	}
	.details .requirement .top .left-l text {
		font-size: 34rpx;
		font-weight: normal;
	}
	.details .requirement .item {
		margin: 0 20rpx;
		padding: 30rpx 0;
		border-bottom: 2rpx solid #ededf5;
	}
	.details .requirement .item .left-l {
		color: #666666;
		font-size: 28rpx;
	}
	.details .requirement .item .right-r {
		color: #666666;
		font-size: 28rpx;
	}
	.details .requirement .item .right-r .copy {
		margin-left: 20rpx;
		padding-left: 20rpx;
		border-left: 2rpx solid #ededf5;
		color: #458fc0;
	}
	
	/* ------------------------------------------------配送 */
	.details .peisong {
		padding: 30rpx 0;
	}
	.details .dian {
		text-align: center;
	}
	.details .dian .iconfont {
		color: #dcdcdc;
		font-size: 20rpx;
		display: inline-block;
		vertical-align: middle;
	}
	.details .dian text {
		display: inline-block;
		margin: 0 10rpx;
		width: 140rpx;
		height: 6rpx;
		background-color: #dcdcdc;
		vertical-align: middle;
	}
	.details .xinxi {
		display: flex;
		justify-content: space-around;
	}
	.details .xinxi .box {
		font-size: 26rpx;
		color: #333333;
	}
	
	/* ----------------------------------------------------------------------底部 */
	.content-bottom {
		position: fixed;
		bottom: 0;
		padding: 20rpx 30rpx;
		width: 100%;
		box-sizing: border-box;
		border-top: 2rpx solid #ededf5;
		background-color: #FFFFFF;
		
	}
	.content-bottom button {
		border-radius: 50rpx;
		width: 100%;
		font-weight: bold;
		background-color: #009bff;
	}
</style>