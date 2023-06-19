<template>
	<view class="home">
		<custom-head-bar></custom-head-bar>
		<view class="wrapper">
			<view class="infoModel">
				<view class="left">
					免费配送
				</view>
				<view class="right">
					<u-icon name="order" color="#576b95" size="24"></u-icon>
					我的订单
				</view>
			</view>
			<view class="scrollLayout">
				<view class="scrollLeft">
					<scroll-view scroll-y class="sCenter">
						<view class="navitem" :class="index == 0 ?'active' : '' " v-for="(item,index) in 50"
							:key="index">
							{{item}}
						</view>
					</scroll-view>
				</view>
				<view class="scrollRight">
					<view class="searchView">
						<u-icon name="search" size="22"></u-icon>
						搜索
					</view>
					<scroll-view scroll-y class="sCenter">
						<view class="productView" v-for="item in 5">
							<u-sticky :customNavHeight="0" z-index="2">
								<view class="proTitle">
									产品名称{{item}}
								</view>
							</u-sticky>

							<view class="proContent">
								<view class="proItem" v-for="item in 3">
									<product-item></product-item>
								</view>
							</view>
						</view>
					</scroll-view>
				</view>
			</view>
		</view>

		<view class="" style="height: 100rpx;background: #576b95;">

		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.home {
		height: 100vh;
		display: flex;
		flex-direction: column;

		.wrapper {
			flex: 1;
			border-radius: 20rpx 20rpx 0 0;
			margin-top: -20rpx;
			position: relative;
			z-index: 2;
			overflow: hidden;

			.infoModel {
				height: 100rpx;
				@include flex-box();
				padding: 0 30rpx;
				color: $text-font-color-1;
				font-size: 32rpx;
				background: #fff;
				border-bottom: 1px solid $border-color-light;

				.right {
					@include flex-box();
					color: $brand-theme-color-aux;
				}
			}

			.scrollLayout {
				@include flex-box();
				height: calc(100% - 100rpx);

				.scrollLeft {
					flex-shrink: 0;
					width: 190rpx;
					height: 100%;
					border-right: 1px solid $border-color-light;

					.navitem {
						font-size: 30rpx;
						padding-left: 30rpx;
						line-height: 100rpx;
						color: $text-font-color-2;
						position: relative;

						&.active {
							color: $text-font-color-1;
							background: #fff;

							&::after {
								content: "";
								width: 6rpx;
								height: 30rpx;
								background: $brand-theme-color;
								position: absolute;
								left: 0;
								top: 50%;
								transform: translateY(-50%);
							}
						}
					}
				}

				.scrollRight {
					flex: 1;
					flex-shrink: 1;
					height: 100%;
					position: relative;
					.searchView {
						position: absolute;
						top: 0;
						right: 30rpx;
						z-index: 3;
						@include flex-box();
						height: 90rpx;
						color: $brand-theme-color-aux;
					}

					.productView {
						padding: 0 30px;

						.proTitle {
							line-height: 90rpx;
							font-size: 30rpx;
							background: #fff;
						}
					}
				}

				.sCenter {
					height: 100%;
				}

			}
		}
	}
</style>