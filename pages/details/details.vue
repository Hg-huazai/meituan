<template>
	<view class="content">
		<view class="example-body">
			<uni-nav-bar left-icon="arrowleft" @clickLeft="back" />
		</view>
		<view class="map">
			<map></map>
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
</style>
