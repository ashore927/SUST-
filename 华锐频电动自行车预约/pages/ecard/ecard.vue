<template>
	<view class="content" scroll-y="true">
		<view class="content1">
			<view class="title">
				<text>电动自行车行驶证</text>
			</view>
			<view class="list">
				<view class="list-name">
					<view class="name">姓&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;名</view>
					<view class="name">身&nbsp;&nbsp;份&nbsp;&nbsp;证&nbsp;&nbsp;号</view>
					<view class="name">联&nbsp;&nbsp;系&nbsp;&nbsp;地&nbsp;&nbsp;址</view>
					<view class="name">车&nbsp;&nbsp;辆&nbsp;&nbsp;车&nbsp;&nbsp;牌</view>
					<view class="name">车&nbsp;&nbsp;辆&nbsp;&nbsp;类&nbsp;&nbsp;型</view>
					<view class="name">整&nbsp;&nbsp;车&nbsp;&nbsp;编&nbsp;&nbsp;码</view>
					<view class="name">注&nbsp;&nbsp;册&nbsp;&nbsp;日&nbsp;&nbsp;期</view>
					<view style="height: 38upx;
									font-size: 25upx;
									display: flex;
									flex-direction: column;
									">登&nbsp;&nbsp;&nbsp;&nbsp;记&nbsp;&nbsp;&nbsp;&nbsp;网&nbsp;&nbsp;&nbsp;点</view>
				</view>
				<view class="list-content">
					<view class="con">{{name}}</view>
					<view class="con">{{id}}</view>
					<view class="con">{{address}}</view>
					<view class="con">{{carId}}</view>
					<view class="con">{{type}}</view>
					<view class="con">{{carNum}}</view>
					<view class="con">{{date}}</view>
					<view style="height: 25upx;
									font-size: 25upx;
									display: flex;
									flex-direction: column;
									">{{register}}</view>
				</view>
				<view class="img-content">
					<view class="img">
						<image mode="widthFix" style="width: 100upx;" src="/static/qrcode.png"></image>
					</view>
					<view class="img-text">{{carId}}</view>
				</view>
			</view>
		</view>
		<view style="padding-top: 40upx; padding-bottom: 60upx;">
			<!-- <image src="../../static/mybike.png" mode="widthFix" style="width: 670upx;"></image> -->
			<!-- <image src="https://hsqs.bmwax.cn/202411182214/1ecb24e6e667c3898e29366de5767f40/mqrcode%2F827857%2F1731939095_6304515831_mybike.png" mode="widthFix" style="width: 670upx;"></image> -->
			<image :src="img" mode="widthFix" style="width: 670upx;"></image>
		</view>
		<navigator style="margin-top: 1800upx; padding-bottom: 10upx;" :url="'/pages/change/change'">
			<view>vesion v1.5</view>
		</navigator>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name: getApp().globalData.name,
				id: getApp().globalData.id,
				address: getApp().globalData.address,
				carId: getApp().globalData.carId,
				type: getApp().globalData.type,
				carNum: getApp().globalData.carNum,
				date: getApp().globalData.date,
				register: getApp().globalData.register,
				img:getApp().globalData.img
			}
		},
		onLoad() {

		},
		methods: {
		    
		    }
		}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding-top: 20upx;
		margin-bottom: 20upx;
		background-color: #f2f9fd;
		width: 100%;
		height: 1800upx;
	}
	.content1{
		margin-top: 50upx;
		padding-bottom: 10upx;
		display: flex;
		flex-direction: column;
		width: 91%;
		border-color: #d7d7d7;
		border-width: 2rpx;
		border-radius: 15upx;
		border-style: solid;
	}
	.title{
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 30upx;
		padding-bottom: 8upx;
		font-size: 49upx;
		font-weight: bold;
	}
	.list{
		display: flex;
		flex-direction: row;
	}
	.list-name{
		display: flex;
		flex-direction: column;
		padding-top: 20upx;
		padding-left: 20upx;
		width: 300upx;
	}
	.name{
		height: 58upx;
		font-size: 30upx;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
	.con{
		height: 58upx;
		font-size: 28upx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 400upx;
	}
	.list-content{
			display: flex;
			flex-direction: column;
			padding-top: 20upx;
			width: 570upx;
	}
	.img-content{
		position: absolute;
		top: 465upx;
		left: 577upx;
	}
	.img{
		display: flex;
		flex-direction: row;
		justify-content: center;
	}
	.img-text{
		font-size: 23upx;
	}
	
</style>
