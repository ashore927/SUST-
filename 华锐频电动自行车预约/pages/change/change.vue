<template>
	<view class="content">
		<view class="form">
			<!-- <form @submit="submitForm"> -->
				<!-- <view class="content"> -->
			          <view class="list">姓&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;名：<input type="text" v-model="formData.name" ></view>
					  <view class="list">身份证号：<input type="text" v-model="formData.id" ></view>
					  <!-- <view class="list">联系地址：<input type="text" v-model="formData.address" ></view> -->
					  <view class="list">联系地址：<textarea v-model="formData.address" rows="2"></textarea></view>
					  <view class="list">车&nbsp;&nbsp;牌&nbsp;号：<input type="text" v-model="formData.carId" ></view>
					  <view class="list">车辆类型：<input type="text" v-model="formData.type" ></view>
					  <view class="list">整车编码：<input type="text" v-model="formData.carNum" ></view>
					  <!-- <view class="list">注册日期：<input type="text" v-model="formData.date" placeholder="Date"></view> -->
					  <view class="list">注册日期：<picker mode="date" v-model="formData.date" @change="onDateChange"><view style="color: #007AFF;">{{ formData.date || '点我选择日期' }}</view></picker></view>
					  <view class="list">登记网点：<input type="text" v-model="formData.register" ></view>
					  <!-- <view class="list">图&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;片：<input type="email" v-model="formData.img" placeholder="Img"></view> -->
					  <view class="list">图&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;片：
							<view class="img-btn">
								<button @click="chooseImage" style="font-size: 23upx; color: #007AFF;">点我选择图片</button>
							</view>
					 </view>
					 <view style="color: #4CD964;">Tips：若值为空，则会使用默认值。</view>
					 <button class="submit-btn" type="submit" @click="submitForm">确认修改</button>
		</view>	
		<view class="upload-img">
			<view v-if="formData.img" style="padding-left: 15upx;">
				<view style="font-size: 40upx; padding-bottom: 10upx;">已选择图片：</view>
				<view style="width: 95vw; word-wrap: break-word; color: #007AFF;">{{ formData.img }}</view>
			</view>
			<view v-if="formData.img" style="padding-top: 15upx; width: 100vw; display: flex; justify-content: center; align-items: center;">
				<image mode="widthFix" style="width: 670upx;" :src="formData.img"/>
			</view>
		</view>
		<view style="display: flex; justify-content: center; align-items: center;">
			<navigator style="margin-top: 600upx; padding-bottom: 10upx;" :url="'/pages/index/index'">
				<view>vesion v1.5</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				formData: {
				        name: '',
				        id: '',
						address: '',
						carId: '',
						type: '',
						carNum: '',
						date: '',
						register: '',
						img: '',
				      }
			}
		},
		methods: {
			onDateChange(event) {
				console.log(event.detail.value)
			      this.formData.date = event.detail.value; // 微信小程序日期格式为 YYYY-MM-DD
			},
			chooseImage() {
			      uni.chooseImage({
			        count: 1, // 选择图片的数量，可以改成多张
			        success: (res) => {
			          // 选择图片成功后，赋值给 formData.img
			          // this.formData.img = res.tempFilePaths[0]; // 获取选择的第一张图片
					  if(res.tempFilePaths[0] != '')
						getApp().globalData.img = res.tempFilePaths[0];
						this.formData.img = res.tempFilePaths[0]; 
			          console.log("选择的图片路径:", getApp().globalData.img);
			        },
			        fail: (err) => {
			          console.log("选择图片失败:", err);
			        },
			      });
			},
			submitForm(event) {
			      // 这里可以使用 this.formData 访问表单数据
				 const app = getApp();
				  // this.formData.address = '111111111222'
				if(this.formData.name != '')
					app.globalData.name = this.formData.name;
				if(this.formData.id != '')
					app.globalData.id = this.formData.id;
				if(this.formData.address != '')
					app.globalData.address = this.formData.address;
				if(this.formData.carId != '')
					app.globalData.carId = this.formData.carId;
				if(this.formData.type != '')
					app.globalData.type = this.formData.type;
				if(this.formData.carNum != '')
					app.globalData.carNum = this.formData.carNum;
				if(this.formData.date != '')
					app.globalData.date = this.formData.date;
				if(this.formData.register != '')
					app.globalData.register = this.formData.register;
			      // console.log(this.formData);
				uni.showModal({
				    title: '修改成功',
				    content: '点击确定，自动返回主页！', // 显示长文本
				    showCancel: false, // 不显示取消按钮
				    success() {
				        setTimeout(() => {
				            console.log('跳转中...');
				            uni.reLaunch({
				                url: '/pages/index/index',
				                success() {
				                    console.log('跳转成功');
				                },
				                fail(err) {
				                    console.error('跳转失败：', err);
				                }
				            });
				        }, 1500);
				    }
				});
			      // 执行提交表单的操作，例如发送到服务器
			      // this.$http.post('your-api-endpoint', this.formData);
			    }
		}
	}
</script>

<style>
.content{
	display: flex;
	flex-direction: column;
	padding-bottom: 30upx;
}
.form{
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 70vw;
	margin-left: 30upx;
	padding: 100upx;
}
.list{
	display: flex;
	flex-direction: row;
	width: 70vw;
	padding-bottom: 30upx;
	/* justify-content: center; */
}
textarea{
	width: 375upx; 
	height: 100upx; 
	border: #EEEEEE; 
	border-style: solid; 
	border-width: 3upx;
	border-radius: 8upx;
}
input{
	width: 50vw;
	height: auto;
	border-style: solid;
	border-width: 3upx;
	border-color: #eeeeee;
	border-radius: 8upx;
}
.submit-btn{
	margin-top: 60upx;
	width: 30vw;
	height: 4vh;
	padding-bottom: 80upx;
}
.img-btn{
	width: auto;
	height: 5upx;
	padding-bottom: 80upx;
}
.upload-img{
	display: flex;
	flex-direction: column;
	width: 70vw;
}
</style>
