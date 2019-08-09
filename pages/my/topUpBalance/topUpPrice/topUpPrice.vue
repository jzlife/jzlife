<template>
	<view>
		<view class="Top">
			<view class="TopShow">
				<view class="TopShowMsgs1">极致生活储值卡</view>
				<view class="TopPrice">50元</view>
				<view class="TopShowMsgs2">充50送10块</view>
			</view>
		</view>
		<view class="BodyAllPrice">
			<radio-group class="AllPrice">
				<radio>50元</radio>
				<radio>100元</radio>
				<radio>200元</radio>
				<radio>500元</radio>
				<radio>1000元</radio>
			</radio-group>
		</view>
		<view class="topUpMethods">
			<view class="MethodsName">
				<view class="MName">支付方式</view>
				<view class="MethodsQuestion">
					<view class="QuestionName">
						充值规则
					</view>
					<image src="../../../../static/images/Ding.png" mode=""></image>
				</view>
				<radio-group class="MethodsClass">
					<radio>
						<image src="../../../../static/images/wx.png" mode=""></image>
						<view class="MethodsClassName">
							微信支付
						</view>
					</radio>
					<radio>
						<image src="../../../../static/images/zfb.png" mode=""></image>
						<view class="MethodsClassName">
							支付宝支付
						</view>
					</radio>
				</radio-group>
			</view>
		</view>
		<view class="Btns" @click="topUpPrice">需支付xx元</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			// 充值金额
			topUpPrice(){
				uni.showModal({
					title:'充值金额',
					content:'您将充值100元',
					showCancel:true
				})
			}
		}
	}
</script>

<style>
	.Top {
		width: 100%;
		height: 320rpx;
		border-bottom: 1rpx solid #B2B2B2;
	}
	.TopShow {
		position: relative;
		top: 25rpx;
		width: 590rpx;
		height: 250rpx;
		border: 1rpx solid #C0C0C0;
		border-radius: 10rpx;
		left: 50%;
		transform: translateX(-50%);
	}
	.TopShowMsgs1 {
		position: absolute;
		top: 10rpx;
		right: 5rpx;
		width: 300rpx;
		height: 40rpx;
		text-align: right;
		font-size: 26rpx;
		line-height: 40rpx;
	}
	.TopPrice {
		position: absolute;
		width: 400rpx;
		height: 100rpx;
		font-size: 60rpx;
		font-weight: bold;
		text-align: center;
		line-height: 100rpx;
		top: 75rpx;
		left: 95rpx;
	}
	.TopShowMsgs2 {
		position: absolute;
		bottom: 10rpx;
		left: 5rpx;
		width: 300rpx;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 26rpx;
	}
	.BodyAllPrice {
		width: 100%;
		height: 100rpx;
	}
	.AllPrice {
		margin-top: 25rpx;
		width: 90%;
		margin-left: 5%;
		display: flex;
		justify-content: space-between;
	}
	
	.AllPrice radio {
		font-size: 24rpx;
	}
	
	.topUpMethods {
		width: 100%;
		height: 230rpx;
		/* border: 1rpx solid black; */
	}
	.MethodsName {
		width: 100%;
		height: 50rpx;
		position: relative;
	}
	.MName {
		position: absolute;
		left: 2%;
		top: 0rpx;
		width: 200rpx;
		height: 50rpx;
		line-height: 50rpx;
		font-size: 26rpx;
	}
	.MethodsQuestion {
		position: absolute;
		top: 0rpx;
		right: 2%;
		width: 200rpx;
		height: 50rpx;
		display: flex;
		justify-content: space-between;
	}
	.QuestionName {
		width: 150rpx;
		height: 50rpx;
		line-height: 50rpx;
		font-size: 26rpx;
		color: #C7C6CD;
		text-align: right;
	}
	.MethodsQuestion image {
		margin-top: 5rpx;
		width: 40rpx;
		height: 40rpx;
	}
	
	.MethodsClass {
		position: absolute;
		top: 60rpx;
		width: 100%;
	}
	
	.MethodsClass radio {
		position: relative;
		width: 100%;
		height: 80rpx;
		padding-left:650rpx;
		padding-top: 20rpx;
		border-bottom: 1rpx solid #B2B2B2;
	}
	
	.MethodsClass radio:nth-of-type(2) {
		border: none;
	}
	
	.MethodsClass radio image {
		position: absolute;
		left: 2%;
		height: 40rpx;
		width: 40rpx;
		top: 20rpx;
	}
	.MethodsClassName {
		width: 200rpx;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 26rpx;
		position: absolute;
		left: 92rpx;
		top: 20rpx;
	}
	.Btns {
		position: fixed;
		bottom: 60rpx;
		left: 50%;
		transform: translateX(-50%);
		width: 400rpx;
		height: 50rpx;
		line-height: 50rpx;
		font-size: 30rpx;
		color: white;
		text-align: center;
		background-color: #0000FF;
	}
</style>
