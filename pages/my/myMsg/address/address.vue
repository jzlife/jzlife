<template>
	<view>
		<view class="top">
			<text>我的地址</text>
		</view>
		<view class="Nav">
			<view class="NavCh">
				<view class="NavCh_Name">希顿国际C座 天府大道中段666号 (2907)</view>
				<view class="moRen">默认地址</view>
				<view class="locationClass">公司</view>
				<view class="UserMsgs">16497165415 杨先生</view>
				<image @click="updateAddress" src="../../../../static/images/Ding.png" mode=""></image>
			</view>
			<view class="NavCh">
				<view class="NavCh_Name">希顿国际C座 天府大道中段666号 (2907)</view>
				<view class="moRen">默认地址</view>
				<view class="locationClass">公司</view>
				<view class="UserMsgs">16497165415 杨先生</view>
				<image src="../../../../static/images/Ding.png" mode=""></image>
			</view>
		</view>
		<view class="newAdd" @click="addAddress">
			<image src="../../../../static/images/Ding.png" mode=""></image>
			<view class="newText">新增地址</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			// 修改地址
			updateAddress() {
				uni.navigateTo({
					url: 'updateAddress/updateAddress'
				})
			},
			// 新增地址
			addAddress() {
				uni.navigateTo({
					url:'addAddress/addAddress'
				})
			}
		}
	}
</script>

<style>
	.top {
		width: 100%;
		height: 60rpx;
		background-color: #B2B2B2;
		color: white;
		font-size: 24rpx;
		line-height: 60rpx;
	}

	.top text {
		margin-left: 2%;
	}

	.Nav {
		width: 100%;
		height: auto;
	}

	.NavCh {
		position: relative;
		width: 100%;
		height: 100rpx;
		border-top: 1rpx solid #C0C0C0;
		border-bottom: 1rpx solid #C0C0C0;
		margin-top: 10rpx;
	}

	.NavCh_Name {
		position: absolute;
		top: 5rpx;
		left: 2%;
		font-size: 24rpx;
		height: 40rpx;
		line-height: 40rpx;
		width: 80%;
	}

	.moRen {
		position: absolute;
		bottom: 5rpx;
		left: 2%;
		background-color: #BBBBBB;
		color: white;
		line-height: 40rpx;
		height: 40rpx;
		width: 126rpx;
		text-align: center;
		font-size: 24rpx;
	}

	.locationClass {
		position: absolute;
		bottom: 5rpx;
		left: 157rpx;
		width: 85rpx;
		height: 40rpx;
		font-size: 24rpx;
		line-height: 40rpx;
		text-align: center;
		color: black;
		border: 1rpx solid #BBBBBB;
	}

	.UserMsgs {
		position: absolute;
		bottom: 5rpx;
		left: 260rpx;
		font-size: 24rpx;
		height: 40rpx;
		width: 300rpx;
		line-height: 40rpx;
	}

	.NavCh image {
		position: absolute;
		/* top: 50%; */
		width: 40rpx;
		height: 40rpx;
		right: 2%;
		top: 30rpx;

	}
	
	/* 新增地址按钮 */
	.newAdd {
		position: fixed;
		bottom: 0rpx;
		left: 0rpx;
		width: 100%;
		height: 90rpx;
		border-top: 1rpx solid #B2B2B2;
	}
	.newAdd image {
		margin-left: 300rpx;
		height: 40rpx;
		width: 40rpx;
		margin-top: 25rpx;
	}
	.newText {
		position: absolute;
		top: 25rpx;
		margin-left: 330rpx;
		width: 150rpx;
		height: 40rpx;
		line-height: 47rpx;
		/* margin-top: 25rpx; */
		font-size: 26rpx;
		text-align: center;
	}
</style>
