<template>
	<view>
		<view class="Nav">
			<view class="NavCh1">
				<view class="NavCh1_Name">头像</view>
				<view class="NavCh1_OurMsgs">
					<image src="../../../static/images/3.jpg" mode=""></image>
				</view>
				<image class="gotoMsgs" @click="updateHeadImgs" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="NavCh1">
				<view class="NavCh1_Name">用户名</view>
				<view class="NavCh1_OurMsgs">张三</view>
				<image class="gotoMsgs" @click="gotoUpdateName" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="NavCh1">
				<view class="NavCh1_Name">性别</view>
				<view class="NavCh1_OurMsgs">{{sex}}</view>
				<picker mode="selector" :range="sexArray" @change="chooseSex">
				<image class="gotoMsgs" src="../../../static/images/jiantou.png" mode=""></image>
					<!-- <view>picker组件</view> -->
				</picker>
			</view>
			<view class="NavCh1">
				<view class="NavCh1_Name">绑定手机</view>
				<view class="NavCh1_OurMsgs" style="width: 190rpx;">13350058238</view>
				<image class="gotoMsgs" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="NavCh1">
				<view class="NavCh1_Name">绑定微信</view>
				<view class="NavCh1_OurMsgs">已绑定</view>
				<image class="gotoMsgs" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="NavCh1">
				<view class="NavCh1_Name">收货地址</view>
				<view class="NavCh1_OurMsgs"></view>
				<image class="gotoMsgs" @click="gotoAddress" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
		</view>
		<view class="Btns">退出登录</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			sexArray:['男','女'],
			sex:'男'
			}
		},
		methods: {
			// 修改头像
			updateHeadImgs() {
				uni.chooseImage({
					count: 1,
					sizeType: ['original'],
					sourceType: ['album'],
					success: function(res) {
						// console.log(res)
						uni.previewImage({
							urls: res.tempFilePaths,
							longPressActions: {
								itemList: ['保存图片'],
								success: function(res) {
									console.log(res)
								},
								fail: function(err) {
									console.log(err)
								}
							}
						})
					}
				})
			},
			// 修改姓名
			gotoUpdateName() {
				uni.navigateTo({
					url: '../../my/myMsg/updateName'
				})
			},
			// 选择性别
			chooseSex(res) {
				console.log(res)
				var index = res.target.value
				this.sex = this.sexArray[index]
			},
			// 进入地址
			gotoAddress() {
				uni.navigateTo({
					url:'address/address'
				})
			},
			

		},
	}
</script>

<style>
	.Nav {
		width: 100%;
		height: auto;
	}

	.NavCh1 {
		position: relative;
		width: 100%;
		height: 130rpx;
		border-bottom: 1rpx solid #B2B2B2;
	}

	.NavCh1_Name {
		position: absolute;
		width: 150rpx;
		height: 40rpx;
		line-height: 40rpx;
		left: 3%;
		top: 45rpx;
		font-size: 26rpx;
	}

	.gotoMsgs {
		position: absolute;
		width: 30rpx;
		height: 30rpx;
		top: 50rpx;
		right: 2%;
	}

	.NavCh1_OurMsgs {
		position: absolute;
		width: 80rpx;
		height: 80rpx;
		top: 25rpx;
		right: 60rpx;
		font-size: 26rpx;
		line-height: 80rpx;
		text-align: center;
	}

	.NavCh1_OurMsgs image {
		width: 100%;
		height: 100%;
		border-radius: 50%;
	}

	.Btns {
		position: fixed;
		bottom: 100rpx;
		width: 400rpx;
		left: 50%;
		transform: translateX(-50%);
		height: 60rpx;
		line-height: 60rpx;
		font-size: 30rpx;
		color: white;
		font-weight: bold;
		text-align: center;
		background-color: #0A98D5;
	}
</style>
