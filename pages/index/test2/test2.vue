<template>
	<view>
		<text>
			<h1>{{longitude}}</h1>
			<h1>{{latitude}}</h1>
		</text>
		<button type="primary" @click="get">选择城市</button>
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
				uni.chooseLocation({
					success: (res) => {
						console.log(res);
						console.log('位置名称：' + res.name);
						console.log('详细地址：' + res.address);
						console.log('纬度：' + res.latitude);
						console.log('经度：' + res.longitude);
						this.longitude = res.longitude
						this.latitude = res.latitude
					}
				})
			}
		}
	}
</script>

<style>

</style>