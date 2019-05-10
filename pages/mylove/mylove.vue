<template>
	<view class="title">
		<image class="logo" src="/static/slogen.gif"></image>
		<view class="example-title">距离妹妹解脱还剩</view>
		<uni-countdown color="#FFFFFF" background-color="#00B26A" border-color="#00B26A" :day="day" :hour="hour" :minute="0" :show-colon="false"></uni-countdown>
		<view class="minie">{{ word }}</view>
		<view class="uni-list">
			<view class="uni-list-cell" v-for="(value, key) in list" :key="key">
				<view class="uni-media-list">
					<view class="uni-media-list-body">
						<view class="uni-media-list-text-top">{{ value.title }}</view>
						<view class="uni-media-list-text-bottom uni-ellipsis">{{ value.content }}</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import uniCountdown from '@/components/uni-countdown/uni-countdown.vue';
export default {
	data() {
		return {
			day: 1,
			hour: 1,
			word: 'aaaaaa',
			list: [
				{
					title: '木屋',
					content: '想要这样一间小木屋，夏天挫冰吃瓜，冬天围炉取暖。',
					img: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/muwu.jpg?imageView2/3/w/200/h/100/q/90'
				},
				{
					title: 'CBD',
					content: '烤炉模式的城，到黄昏，如同打翻的调色盘一般。',
					img: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/cbd.jpg?imageView2/3/w/200/h/100/q/90'
				}
			]
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
		
		this.word = "丢雷斗魔"
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
.minie {
	font-size: 36upx;
	color: #000;
}
</style>
