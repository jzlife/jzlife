<template>
	<view>
		<view class="Top">
			<view class="TopName">兑换码:</view>
			<input type="text" value="" placeholder="单行输入"/>
			<button type="primary" class="duihuan">兑换</button>
		</view>
		<view class="Body">
			<text>余额</text>
			<view class="Price">￥35979.35</view>
		</view>
		<view class="btns" @click="gotoBalance">立即充值</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			// 余额充值
			gotoBalance() {
				uni.navigateTo({
					url:'topUpPrice/topUpPrice'
				})
			}
		}
	}
</script>

<style>
	.Top {
		position: relative;
		width: 100%;
		height: 80rpx;
		border-bottom: 1rpx solid #B2B2B2;
	}
	.TopName {
		position: absolute;
		width: 100rpx;
		height: 40rpx;
		top: 30rpx;
		left: 2%;
		font-size: 24rpx;
		line-height: 40rpx;
	}
	.Top input {
		position: absolute;
		top: 20rpx;
		width: 426rpx;
		font-size: 26rpx;
		height: 40rpx;
		border: 1rpx solid #B2B2B2;
		left: 110rpx;
	}
	.duihuan {
		width: 120rpx;
		height: 40rpx;
		position: absolute;
		right: 2%;
		line-height: 40rpx;
		font-size: 26rpx;
		top: 30rpx;
	}
	.Body{
		position: relative;
		width: 94%;
		height: 130rpx;
		margin-left: 3%;
		border: 1rpx solid #B2B2B2;
		border-radius: 10rpx;
		margin-top: 10rpx;
	}
	.Body text {
		position: absolute;
		width: 60rpx;
		height: 40rpx;
		line-height: 40rpx;
		top: 45rpx;
		left: 2%;
		font-size: 24rpx;
	}
	.Price {
		width: 300rpx;
		height: 40rpx;
		line-height: 40rpx;
		position: absolute;
		top: 45rpx;
		left: 90rpx;
		font-size: 36rpx;
		color: #0000FF;
		font-weight: bold;	
	}
	
	.btns {
		position: fixed;
		bottom: 60rpx;
		left: 50%;
		transform: translateX(-50%);
		width: 400rpx;
		height: 60rpx;
		line-height: 60rpx;
		color: white;
		background-color: #0A98D5;
		text-align: center;
		font-size: 30rpx;
	}
</style>
