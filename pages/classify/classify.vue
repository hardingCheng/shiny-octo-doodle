<template>
	<view class="classLayout pageBg">
		<!-- #ifndef MP-TOUTIAO -->
		<custom-nav-bar title="分类"></custom-nav-bar>
		<!-- #endif -->
		<view class="classify">
			<theme-item v-for="i in 15"></theme-item>
		</view>
	</view>
</template>

<script setup>
	import themeItem from '../../components/theme-item/theme-item.vue';
</script>

<style scoped lang="scss">
	.classify {
		padding: 30rpx;
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 15rpx;
	}
</style>