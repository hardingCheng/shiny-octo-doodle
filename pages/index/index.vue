<template>
	<view class="homeLayput">
		<view class="banner">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" :circular="true">
				<swiper-item v-for="i in 5">
					<image src="../../common/images/banner2.jpg" mode="aspectFill" />
				</swiper-item>
			</swiper>
		</view>
		<view class="notice">
			<view class="left">
				<uni-icons type="sound-filled" size="20"></uni-icons>
				<text class="text">公告</text>
			</view>
			<view class="center">
				<swiper vertical autoplay interval="2000" duration="300" circular>
					<swiper-item v-for="item in 3" :key="item._id">
						<navigator :url="'/pages/notice/detail?id='+item._id">
							121212
						</navigator>
					</swiper-item>
				</swiper>
			</view>
			<view class="right">
				<uni-icons type="right" size="16" color="#333"></uni-icons>
			</view>
		</view>
		<view class="select">
			<common-title>
				<template #name>每日推荐</template>
				<template #custom>
					<view class="date">
						<uni-icons type="calendar" size="18"></uni-icons>
						<view class="text">
							<uni-dateformat :date="Date.now()" format="dd日"></uni-dateformat>
						</view>
					</view>
				</template>
			</common-title>
			<view class="content">
				<scroll-view scroll-x>
					<view class="box" v-for="item in 20" :key="item._id">
						<image src="../../common/images/classify1.jpg" mode="aspectFill" />
					</view>
				</scroll-view>
			</view>
		</view>
		<view class="theme">
			<common-title>
				<template #name>专题精选</template>
				<template #custom>
					<navigator url="/pages/classify/classify" open-type="reLaunch" class="more">More+</navigator>
				</template>
			</common-title>

			<view class="content">
				<scroll-view scroll-x>
					<view class="box" v-for="item in 20" :key="item._id">
						<image src="../../common/images/classify1.jpg" mode="aspectFill" />
					</view>
				</scroll-view>
			</view>

		</view>
	</view>
</template>

<script setup>
	import commonTitle from '../../components/common-title/common-title/common-title.vue';
</script>

<style scoped lang="scss">
	.homeLayput {
		.banner {
			width: 750rpx;
			padding: 30rpx 0;

			swiper {
				width: 750rpx;
				height: 340rpx;

				&-item {
					padding: 0 30rpx;
					width: 100%;
					height: 100%;

					image {
						width: 100%;
						height: 100%;
						border-radius: 10rpx;
					}
				}
			}
		}

		.notice {
			width: 690rpx;
			height: 80rpx;
			line-height: 80rpx;
			background: #f9f9f9;
			margin: 0 auto;
			border-radius: 80rpx;
			display: flex;

			.left {
				width: 140rpx;
				display: flex;
				align-items: center;
				justify-content: center;

				:deep() {
					.uni-icons {
						color: $brand-theme-color !important;
					}
				}

				.text {
					color: $brand-theme-color;
					font-weight: 600;
					font-size: 28rpx;
				}
			}

			.center {
				flex: 1;

				swiper {
					height: 100%;

					&-item {
						height: 100%;
						font-size: 30rpx;
						color: #666;
						overflow: hidden;
						white-space: nowrap;
						text-overflow: ellipsis;
					}
				}
			}

			.right {
				width: 70rpx;
				display: flex;
				align-items: center;
				justify-content: center;
			}
		}

		.select {
			padding-top: 50rpx;

			.date {
				color: $brand-theme-color;
				display: flex;
				align-items: center;

				:deep() {
					.uni-icons {
						color: $brand-theme-color !important;
					}
				}

				.text {
					margin-left: 5rpx;
				}
			}

			.content {
				width: 720rpx;
				margin-left: 30rpx;
				margin-top: 30rpx;

				scroll-view {
					white-space: nowrap;

					.box {
						width: 200rpx;
						height: 430rpx;
						display: inline-block;
						margin-right: 15rpx;

						image {
							width: 100%;
							height: 100%;
							border-radius: 10rpx;
						}
					}

					.box:last-child {
						margin-right: 30rpx;
					}
				}
			}
		}

		.theme {
			padding: 50rpx 0;

			.more {
				font-size: 32rpx;
				color: #888;

			}

			.content {
				// margin-top: 30rpx;
				// padding: 0 30rpx;
				// display: grid;
				// gap: 15rpx;
				// grid-template-columns: repeat(3, 1fr);
				width: 720rpx;
				margin-left: 30rpx;
				margin-top: 30rpx;

				scroll-view {
					white-space: nowrap;

					.box {
						width: 200rpx;
						height: 430rpx;
						display: inline-block;
						margin-right: 15rpx;

						image {
							width: 100%;
							height: 100%;
							border-radius: 10rpx;
						}
					}

					.box:last-child {
						margin-right: 30rpx;
					}
				}
			}
		}
	}
</style>