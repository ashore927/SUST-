<template>
	<view class="content">
		<view class="user-area">
			<image class="logo" src="/static/user.png"></image>
			<text class="wlc-text">您好，{{name}}</text>
			<text class="jf-text">缴费凭证 ></text>
		</view>
		
		<view class="body">
			<view class="body-content">
				<view class="body-title">
					<view class="body-title1">电动自行车</view><view style="margin-top: 8upx;">|</view>
					<view class="body-title1">已登记 1 辆</view>
				</view>
				<view class="body-main">
					<view class="main-add">
						<view class="add-text1">+ 新增登记车辆</view>
						<view class="add-text2">购置的新车和转让车辆登记</view>
					</view>
					<view class="main-number">
						<view class="number-content">
							<view class="number-name">车&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;牌&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;号&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;：
							    </br><view style="margin-top: 20upx;">车&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;架&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;号&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;：</view>
							</view>
							<view class="numbers">{{carId}}</br>
								<view style="margin-top: 20upx;">{{carNum}}</view>
							</view>
						</view>
						<view class="card-bg">
							<view class="card-content">
								<navigator class="e-card" :url="'/pages/ecard/ecard'">
									<image class="card-img" src="/static/e_card.png"></image>
									<view>电子行驶证</view>
								</navigator>
							</view>
							<view class="card-content">
								<view class="e-card">
									<image class="card-img" src="/static/work.png"></image>
									<view>登记业务</view>
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				name: getApp().globalData.name,
				carId: getApp().globalData.carId,
				carNum: getApp().globalData.carNum,
			}
		},
		onLoad() {

		},
		methods: {
		    // tz: function (event) {
		    //   // `this` 在方法里指当前 Vue 实例
		    //   console.error('弹窗失败', err);
		    //   // `event` 是原生 DOM 事件
		    //   if (event) {
		    //       console.error('弹窗失败', err);
		    //   }
		    // }
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
		height: 80upx;
		width: 55upx;
		margin-top: 20upx;
		margin-left: 20upx;
		margin-right: 20upx;
		/* margin-bottom: 50rpx; */
	}

	.user-area {
		padding-top: 10upx;
		height: 120upx;
		width: 100%;
		display: flex;
		flex-direction: row;
		/* align-items: center; */
		/* justify-content: center; */
	}

	.wlc-text {
		margin-top: 40upx;
		margin-left: 15upx;
		font-size: 36upx;
		color: #8f8f94;
	}
	
	.jf-text {
		margin-top: 40upx;
		margin-left: 280upx;
		font-size: 30upx;
		color: #438ef7;
	}
	
	.body
	{
		display: flex;
		flex-direction: row;
		background-color: #f3fafd;
		height: 1215upx;
		width: 100%;
	}
	.body-content{
		margin-top: 15upx;
		margin-left: 20upx;
		margin-right: 20upx;
		background-color:#c0dff9 ;
		height: 1200upx;
		width: 100%;
		border-radius: 6upx;
	}
	.body-title{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		width: 100%;
		background-color: #99bef2;
		border-radius: 8upx;
	}
	.body-title1{
		margin-top: 10upx;
		margin-bottom: 10upx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		width: 49.5%;
		font-weight: 520;
	}
	.body-main{
		margin-left: 8upx;
		margin-right: 8upx;
		background-color: white;
		display: flex;
		flex-direction: column;
		align-items: center;
		width: 98%;
		height: 1135upx;
	}
	.main-add{
		background-color: #e5effd;
		margin-top: 35upx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 88%;
		height: 280upx;
		border-radius: 8upx;
		border:3upx solid #99bef2;
	}
	.add-text1{
		font-size: 35upx;
		color: #4188dc;
		font-weight: bold;
	}
	.add-text2{
		margin-top: 8upx;
		font-size: 30upx;
		color: #4188dc;
	}
	.main-number{
		display: flex;
		flex-direction: column;
		margin-top: 35upx;
		width: 88%;
		height: 250upx;
		border-radius: 8upx;
		border:3upx solid #99bef2;
	}
	.number-content{
		display: flex;
		flex-direction: row;
		margin-top: 15upx;
	}
	.number-name{
		display: flex;
		flex-direction: column;
		width: 40%;
		color: #4188dc;
		font-size: 28upx;
		margin-left: 30upx;
	}
	.numbers{
		display: flex;
		flex-direction: column;
		width: 30%;
		color: #000000;
		font-size: 28upx;
		margin-left: 10upx;
	}
	.card-bg{
		margin-top: 10upx;
		margin-left: 32upx;
		margin-right: 10upx;
		display: flex;
		flex-direction: row;
		width: 90%;
		height: 120upx;
		align-items: center;
		justify-content: space-between;
		/* background-color: #000000; */
	}
	.card-content{
		width: 250upx;
		/* background-color: #007AFF; */
		align-items: center;
		justify-content: center;
	}
	.e-card{
		background-color: #e5effd;
		width: 100%;
		height: 80upx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		color: #5674c9;
		font-size: 28upx;
		border-radius: 8upx;
		border:3upx solid #99bef2;
	}
	.card-img{
		margin-right: 10upx;
		width: 53upx;
		height: 40upx;
	}
</style>
