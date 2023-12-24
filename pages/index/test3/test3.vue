<template>
	<view>
		<button type="primary" @click="get">打开当前位置</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				longitude: 0,
				latitude: 0,
			}
		},
		methods: {
			get() {
				uni.getLocation({
					type: 'gcj02',
					success: function(res) {
						const latitude = res.latitude;
						const longitude = res.longitude;
						uni.openLocation({
							latitude: latitude,
							longitude: longitude,
							success: function() {
								console.log('success');
							}
						});
					},
					fail: (err) => {
						console.log(err);
					}
				});
			}
		}
	}
</script>

<style>

</style>