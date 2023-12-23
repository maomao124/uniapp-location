<template>
	<view>
		<text>
			<h1>{{longitude}}</h1>
			<h1>{{latitude}}</h1>
		</text>
		<button type="primary" @click="get">获取地址</button>
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
					success: (res) => {
						console.log("返回数据：",res);
						console.log('当前位置的经度：' + res.longitude);
						console.log('当前位置的纬度：' + res.latitude);
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