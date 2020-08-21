<template>
	<view class="uni-padding-wrap uni-common-pb">

	</view>
</template>
<script>
	export default {
		data() {
			return {

			}
		},
		onShareAppMessage() {
			return {
				title: '欢迎体验uni-app',
				path: '/pages/home/index'
			}
		},
		onNavigationBarButtonTap(e) {
			uni.navigateTo({
				url: '/pages/about/about'
			});
		},
		methods: {

		}
	}
</script>

<style>
	page {
		height: auto;
		min-height: 100%;
	}
</style>
