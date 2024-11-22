<template>
	<view class="content" scroll-y="true">
		<view class="user-area">
			<image class="logo" src="/static/user.png"></image>
			<text class="wlc-text">您好，{{name}}</text>
		</view>
		<view class="my-bike">
			<navigator class="my-bike-bg" :url="'/pages/mybike/mybike'">
				<image class="bike-img" src="/static/bike.png"></image>
				<text class="bike-text">我的电动自行车</text>
				<image class="jt-img" src="/static/jiantou.png"></image>
			</navigator>
		</view>
<!-- 		<view class="register">
			<image class="register-img" src="/static/register.png"></image>
		</view>
		<view class="slogan-area">
			<image class="slogan" src="/static/slogan.png"></image>
		</view> -->
		<view class="list-img">
<!-- 			<image class="list-img1" src="/static/list1n.png"></image>
			<image class="list-img2" src="/static/list2n.png"></image> -->
			<image style="width: 100vw;" mode="widthFix" src="/static/list1n.png"></image>
			<image style="width: 100vw;" mode="widthFix" src="/static/list2n.png"></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
				name: getApp().globalData.name
			}
		},
		onLoad() {

		},
		methods: {
		    tz: function (event) {
		      // `this` 在方法里指当前 Vue 实例
		      console.error('弹窗失败', err);
		      // `event` 是原生 DOM 事件
		      if (event) {
		          console.error('弹窗失败', err);
		      }
		    }
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		/* align-items: center; */
		/* justify-content: center; */
	}

	.logo {
		height: 80rpx;
		width: 55rpx;
		margin-top: 20rpx;
		margin-left: 20rpx;
		margin-right: 20rpx;
		/* margin-bottom: 50rpx; */
	}

	.user-area {
		height: 48px;
		width: 100%;
		display: flex;
		flex-direction: row;
		/* align-items: center; */
		/* justify-content: center; */
	}

	.wlc-text {
		margin-top: 40rpx;
		margin-left: 15rpx;
		font-size: 36rpx;
		color: #8f8f94;
	}
	
	.my-bike {
		height: 130px;
		width: 100%;
		background-color:#f1fafe;
		display: flex;
		margin-top: 40rpx;
		flex-direction: row;
		align-items: center;
		/* justify-content: center; */
	}
	
	.my-bike-bg {
		height: 100px;
		width: 95%;
		margin-left: 20rpx;
		margin-right: 20rpx;
		background-color:#60acf2;
		display: flex;
		flex-direction: row;
		align-items: center;
		border-radius: 18px;
		/* justify-content: center; */
	}
	
	.bike-img {
		height: 80rpx;
		width: 80rpx;
		margin-left: 70rpx;
		/* margin-bottom: 50rpx; */
	}
	.bike-text {
		margin-left: 100rpx;
		font-size: 40rpx;
		color: #ffffff;
	}
	
	.jt-img {
		height: 40rpx;
		width: 30rpx;
		margin-left: 140rpx;
	}
	
	.register {
		height: 110px;
		width: 100%;
		background-color:#FFFFFF;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
	}
	
	.register-img {
		height: 100%;
		width: 100%;
	}
	
	.slogan-area {
		height: 40px;
		width: 100%;
		background-color:#FFFFFF;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
	}
	.slogan{
		height: 100%;
		width: 100%;
	}
	.list-img1{
		height: 1100rpx;
		width: 100%;
	}
	.list-img2{
		height: 550rpx;
		width: 100%;
	}

	
</style>
