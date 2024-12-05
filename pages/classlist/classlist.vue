<template>
	<view class="classlist">
		<view class="content">
			<navigator :url="'/pages/preview/preview?id='+item._id" class="item" 
			v-for="item in 5"
			>			
				<image src="../../common/images/preview2.jpg" mode="aspectFill"></image>
			</navigator>
		</view>
		<view class="safe-area-inset-bottom"></view>
	</view>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.classlist{
	.content{
		display: grid;
		grid-template-columns: repeat(3,1fr);
		gap:5rpx;
		padding:5rpx;
		.item{
			height: 440rpx;
			image{
				width: 100%;
				height: 100%;
				display: block;
			}
		}
	}
}
</style>
