<template>
	<view class="page">
		<view class="uni-list">
			<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(value, key) in list" :key="key" @click="goDetail(value)">
				<view class="uni-media-list">
					<view class="uni-media-list-logo"><image v-if="showImg" :src="value.img"></image></view>
					<view class="uni-media-list-body">
						<view class="uni-media-list-text-top">{{ value.title }}</view>
						<view class="uni-media-list-text-bottom uni-ellipsis">{{ value.content }}</view>
					</view>
				</view>
			</view>
		</view>
		<view class="content" v-if="list.length <= 0" @click="toCreate">{{ title }}</view>
		<navigator class="toWrite" url="../create/create"></navigator>
	</view>
</template>

<script>
export default {
	data() {
		return {
			title: '和我分享下心情吧',
			showImg: true,
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
	onLoad() {},
	methods: {
		goDetail: function(e) {
			// let detail = {
			// 	author_name: e.author_name,
			// 	cover: e.cover,
			// 	id: e.id,
			// 	post_id: e.post_id,
			// 	published_at: e.published_at,
			// 	title: e.title
			// };
			uni.navigateTo({
				url: '../detail/detail'
			});
		},
		toCreate() {
			uni.navigateTo({
				url: '../create/create'
			});
		}
	}
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
	font-size: 36upx;
	color: #8f8f94;
}
.toWrite {
	width: 100rpx;
	height: 100rpx;
	background: url(../../static/write.png) no-repeat;
	padding: 0;
	background-size: cover;
	position: fixed;
	right: 30rpx;
	bottom: 100rpx;
	border-bottom: 0;
	border-top: 0;
}
</style>
