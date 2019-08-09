<template>
	<view class="Nav">
		<view class="Names">
			用户名    <input type="text" value="" placeholder="单行输入"/>
		</view>
		<view class="Btns">
			确认
		</view>
	</view>
</template>

<script>
</script>

<style>
	.Nav {
		width: 100%;
		height: 100rpx;
		border-bottom: 1rpx solid #B2B2B2;
	}
	.Names {
		position: relative;
		margin-left: 30rpx;
		margin-top: 60rpx;
		height: 60rpx;
		width: 400rpx;
		font-size: 26rpx;
		line-height: 60rpx;
	}
	input {
		position: absolute;
		top: 0rpx;
		left: 100rpx;
		width: 400rpx;
		height: 40rpx;
		font-size: 26rpx;
		border: 1rpx solid #6D6D72;
	}
	.Btns {
		text-align: center;
		line-height: 60rpx;
		height: 60rpx;
		width: 400rpx;
		position: fixed;
		top: 200rpx;
		left: 50%;
		transform: translateX(-50%);
		background-color: #0A98D5;
		color: white;
		font-size: 30rpx;
		font-weight: bold;
	}
</style>
