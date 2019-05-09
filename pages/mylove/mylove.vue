<template>
	<view class="title">
		<image class="logo" src="/static/slogen.gif"></image>
		<view class="example-title">距离妹妹解脱还剩</view>
		<uni-countdown color="#FFFFFF" background-color="#00B26A" border-color="#00B26A" :day="day" :hour="hour" :minute="0" :show-colon="false"></uni-countdown>
	</view>
</template>

<script>
import uniCountdown from '@/components/uni-countdown/uni-countdown.vue';
export default {
	data() {
		return {
			day: 1,
			hour: 1
		};
	},
	onLoad() {
		var endDate = new Date(2019, 5, 6, 18, 0, 0);
		var Today = new Date();

		var leftTime = endDate.getTime() - Today.getTime();
		var leftSecond = parseInt(leftTime / 1000);
		this.day = Math.floor(leftSecond / (60 * 60 * 24));
		leftSecond = leftSecond % (3600 * 24);
		this.hour = Math.floor(leftSecond / 3600);
	},
	methods: {},
	components: { uniCountdown }
};
</script>

<style>
.content {
	text-align: center;
	height: 400upx;
}

.logo {
	height: 200upx;
	width: 200upx;
	margin-top: 200upx;
}

.title {
	text-align: center;
	font-size: 36upx;
	color: #8f8f94;
}
</style>
