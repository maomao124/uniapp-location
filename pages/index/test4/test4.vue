<template>
	<view>
		<text>
			<h1>{{longitude}}</h1>
			<h1>{{latitude}}</h1>
		</text>
		<button type="primary" @click="button1">监听实时地理位置变化事件</button>
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
			button1() {
				uni.onLocationChange((res) => {
					console.log('纬度：' + res.latitude);
					console.log('经度：' + res.longitude);
					this.longitude = res.longitude;
					this.latitude = res.latitude;
				})
				console.log("设置完成");
			}
		}
	}
</script>

<style>

</style>