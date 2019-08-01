<template>
	<view class="index">
		<view class="top">
			<view class="banner">
				<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
					<swiper-item v-for="(item, index) in adList" :key="index">
						<a :href="item.url">
							<image :src="item.picture" mode="scaleToFill"></image>
						</a>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<!-- 定位 -->
		<view class="location" @click="correctLocation">
			<image :src="locationImg" class="locaImg"></image>
			{{adressName}}
			<text class="locaText">></text>
		</view>
		<!-- 下单 -->
		<view class="subfieldTitle" @click="jumpToMenu">
			<text class="subfieldText">现在下单</text>
			<text class="subfieldText">ORDERNOW</text>
			<image :src="orderNowImg" class="subfieldImg"></image>
		</view>
		<!-- 卡券包 -->
		<view class="subfieldTitle" @click="jumpToBag">
			<text class="subfieldText">卡券包</text>
			<text class="subfieldText">WALLET</text>
			<image :src="cardBagImg" class="subfieldImg"></image>
		</view>
		<!-- 赠送 -->
		<view class="subfieldTitle" @click="jumpToGift">
			<text class="subfieldText">卡券包</text>
			<text class="subfieldText">WALLET</text>
			<image :src="complimentImg" class="subfieldImg"></image>
		</view>
		<!-- saaaaaaaaa -->
	</view>
</template>

<script>
	var QQMapWX = require('../../qqmap-wx-jssdk.min.js');
	var qqmapsdk
	export default {
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 1500,
				adressName: 'as',
				locationImg:'../../static/index/dingwei.png',
				orderNowImg:'../../static/index/star.png',
				cardBagImg:'../../static/index/star.png',
				complimentImg:'../../static/index/star.png',
				adList: [{
						url: "",
						picture: "../../static/index/lunbo1.png",

						index: 1
					},
					{
						url: "",
						picture: "../../static/index/lunbo2.png",
						index: 2
					},
					{
						url: "",
						picture: "../../static/index/lunbo3.png",
						index: 3
					},
				],
			}
		},
		onLoad() {
			var that = this
			qqmapsdk = new QQMapWX({
				key: 'KCNBZ-LHSRG-UPSQM-IPIIV-HSXIK-RGBAG'
			});
			uni.getLocation({
				type:"gcj02",
				success (res) {
					qqmapsdk.reverseGeocoder({
						location:{
							latitude:res.latitude,
							longitude:res.longitude
						},
						success(res){
							that.adressName=res.result.formatted_addresses.recommend;
							console.log(that.adressName)
						},
						fail(err){
							console.log(err);
						}
					})
				}
			});
			
		},
		methods: {
			correctLocation(){
				uni.navigateTo({
					url: './location?cityId='+1
				});
			}
		}
	}
</script>

<style>
	.banner {
		height: 349rpx;
		background: #BBBBBB;
	}

	a {
		display: inline-block;
		width: 100%;
		height: 349rpx;
	}

	.swiper {
		height: 349rpx;
	}

	image {
		width: 100%;
		height: 349rpx;
	}

	.location {
		line-height: 116rpx;
		width: 100%;
		height: 116rpx;
		border-bottom: #BBBBBB solid 1px;
		font-size: 25rpx;
		color: rgba(16,16,16,1);
	}
	.locaImg{
		width: 30px;
		height: 30px;
		line-height: 116rpx;
		display: inline-block;
		vertical-align: middle;
	}
	.locaText{
		width: 24px;
		height: 24px;
		float: right;
	}
	.subfieldTitle{
		line-height: 114rpx;
		width: 100%;
		height: 164rpx;
		border-bottom: #BBBBBB solid 1px;
		font-size: 33rpx;
		color: rgba(16,16,16,1);
	}
	.subfieldText{
		width: 183rpx;
		height: 43rpx;
		display: block;
		margin-left: 16rpx;
	}
	.subfieldImg{
		float: right;
		width: 94rpx;
		height: 94rpx;
		margin-top: -52rpx;
		border: rgba(187, 187, 187, 1) solid 1px;
		border-radius: 60rpx;
	}
</style>
