<template>
	<view class="customHead">
		<view class="bg">
			<image class="bgimg" src="../../static/images/header-bar.webp" mode="aspectFill"></image>
		</view>
	</view>
</template>

<script>
	export default {
		name:"custom-head-bar",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.customHead{
	height: 200rpx;
	overflow: hidden;
	.bg{
		width: 100%;
		height: 100%;
		background: $brand-theme-color;
		.bgimg{
			width: 100%;
			height: 100%;
			filter: blur(10rpx);
			transform: scale(1.9);
		}
	}
}
</style>