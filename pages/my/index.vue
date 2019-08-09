<template>
	<view>
		<view class="TopHead_Name">
			<image class="TopHeadImgs" src="../../static/images/3.jpg" mode=""></image>
			<view class="TopName">技术的覅胡说八道和就</view>
			<image class="LingDang"  @click="gotoMessage" src="../../static/images/Ding.png" mode=""></image>
			<image class="TopRight" @click="gotoMyMsgs" src="../../static/images/jiantou.png" mode=""></image>
		</view>
		<view class="BodyImgs">
			<image src="../../static/images/2.jpg" mode=""></image>
		</view>
		<view class="Price_Card">
			<view class="Price" @click="topUpBalance">
				<view class="PriceNum">￥9999</view>
				<view class="PriceName">余额</view>
			</view>
			<view class="Card">
				<view class="CardNum">10000</view>
				<view class="CardName">卡券</view>
			</view>
		</view>
		<view class="BodyNav">
			<view class="NavCh1">
				<image class="NavCh1Name_Imgs" src="../../static/images/selectedCart.png" mode=""></image>
				<view class="NavCh1_Name">优惠商城</view>
				<image class="GotoDetail" src="../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="NavCh1">
				<image class="NavCh1Name_Imgs" src="../../static/images/selectedCart.png" mode=""></image>
				<view class="NavCh1_Name">我的拼团</view>
				<image class="GotoDetail" src="../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="NavCh1">
				<image class="NavCh1Name_Imgs" src="../../static/images/selectedCart.png" mode=""></image>
				<view class="NavCh1_Name">设置</view>
				<image class="GotoDetail" src="../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="NavCh1">
				<image class="NavCh1Name_Imgs" src="../../static/images/selectedCart.png" mode=""></image>
				<view class="NavCh1_Name">理赔规则</view>
				<image class="GotoDetail" src="../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="NavCh1">
				<image class="NavCh1Name_Imgs" src="../../static/images/selectedCart.png" mode=""></image>
				<view class="NavCh1_Name">客服与帮助</view>
				<image class="GotoDetail" src="../../static/images/jiantou.png" mode=""></image>
			</view>
		</view>
		<view class="Footer">
			<image src="../../static/images/2.jpg" mode=""></image>
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
			// 进入我的个人信息
			gotoMyMsgs() {
				uni.navigateTo({
					url:'myMsg/myMsg'
				})
			},
			// 进入消息中心
			gotoMessage() {
				uni.navigateTo({
					url:'myMsg/address/message/message'
				})
			},
			// 余额重置
			topUpBalance() {
				uni.navigateTo({
					url:'topUpBalance/topUpBalance'
				})
			}
		}
	}
</script>

<style>
	.TopHead_Name {
		position: relative;
		width: 100%;
		height: 150rpx;
		border: 1rpx solid black;
	}
	.TopHeadImgs {
		position: absolute;
		top: 25rpx;
		left: 2%;
		width: 100rpx;
		height: 100rpx;
		border-radius: 50%;
	}
	.TopName {
		position: absolute;
		top: 60rpx;
		left: 150rpx;
		width: 300rpx;
		height: 30rpx;
		line-height: 30rpx;
		font-size: 24rpx;	
	}
	.LingDang {
		position: absolute;
		top: 20rpx;
		right: 2%;
		width: 30rpx;
		height: 30rpx;
	}
	.TopRight {
		position: absolute;
		top: 90rpx;
		right: 2%;
		width: 40rpx;
		height: 40rpx;
	}
	/* bodyImgs */
	.BodyImgs {
		width: 100%;
		height: 90rpx;
	}
	.BodyImgs image {
		width: 100%;
		height: 100%;
	}
	/* 余额  卡券  */
	.Price_Card {
		width: 100%;
		height: 130rpx;
		display: flex;
		justify-content: space-between;
	}
	.Price, .Card {
		width: 50%;
		border: 1rpx solid #929292;
		
	}
	.PriceNum,.CardNum {
		width: 100%;
		height: 70rpx;
		text-align: center;
		line-height: 108rpx;
		font-size: 36rpx;
		font-weight: bold;
	}
	.PriceName,.CardName {
		width: 100%;
		height: 50rpx;
		line-height: 50rpx;
		text-align: center;
		font-size: 30rpx;
		font-weight: bold;
	}
	/* 更多功能部分 */
	.BodyNav {
		width: 100%;
		height: auto;
		
	}
	.NavCh1 {
		position: relative;
		width: 100%;
		height: 110rpx;
		border: 1rpx solid #B2B2B2;
	}
	.NavCh1:nth-of-type(3) {
		margin-top: 12rpx;
	}
	.NavCh1Name_Imgs {
		position: absolute;
		top: 34rpx;
		left: 2%;
		width: 40rpx;
		height: 40rpx;
	}
	.NavCh1_Name {
		position: absolute;
		width: 200rpx;
		height: 40rpx;
		top: 42rpx;
		left: 70rpx;
		font-size: 27rpx;
		font-weight: bold;
		line-break: 40rpx;
	}
	.GotoDetail {
		position: absolute;
		width: 30rpx;
		height: 30rpx;
		top: 40rpx;
		right: 2%;
	}
	/* 底部信息 */
	.Footer {
		width: 100%;
		height: 165rpx;
		margin-top: 15rpx;
	}
	.Footer image {
		width: 100%;
		height: 100%;
	}
</style>
