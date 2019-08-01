<template>
	<view class="location">
		
		<view class="locaTop">
			<view class="citySearch" @click="jumpSearchCity" >
			{{getCityName}}
			</view>
			<input class="addressSearch"  @click="jumpSearchAddress" placeholder="小区/写字楼/学校 等">
			</input>
		</view>
		<!-- 当前定位 -->
		<view class="presentLocation">
			<text class="preLocaTitle">当前定位</text>
			<view class="preLocaName">
			{{preLocaName}}
			</view>
			<view class="relocation" @click="relocation">重新定位</view>
		</view>
		<!-- 取件地址 -->
		<view class="shippingAddress">
			<view class="shippingAddressTop">
				<text class="shipAddressTitle">取件地址</text>
				<view class="manageAddress" @click="manageAddress">管理地址</view>
			</view>
			<!-- <view class="addressList" v-for="(item, index) in rooftimeCards">
				<view class></view>
			</view> -->
		</view>
	</view>
</template>

<script>
	var QQMapWX = require('../../qqmap-wx-jssdk.min.js');
	var qqmapsdk
	export default {
		data() {
			return {
				getCityId:'',
				getCityName:'',
				preLocaName:'',
				cityList:[
					{
						cityId:"1",
						cityName:"成都"
					},
					{
						cityId:"2",
						cityName:"重庆"
					},
					{
						cityId:"3",
						cityName:"绵阳"
					},
				]
				
			}
		},
		onLoad(option) {
			this.getCityId=option.cityId
			var that = this
			var i=0;
			for(i=0;i<that.cityList.length;i++){
				if(that.cityList[0].cityId==that.getCityId){
					that.getCityName=that.cityList[0].cityName;
				}
			}
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
							console.log(res);
							that.preLocaName=res.result.address_component.city+res.result.formatted_addresses.recommend;
						},
						fail(err){
							console.log(err);
						}
					})
				}
			});
			
		},
	}
</script>

<style>
	.locaTop{
		width: 100%;
		height: 116rpx;
		border-bottom: #BBBBBB solid 1px;
	}
	.citySearch{
		position:absolute;
		width: 25%;
		height: 116rpx;
		line-height: 110rpx;
		font-size: 32rpx;
		border-right: #BBBBBB solid 1px;
		text-align: center;
		display: inline-block;
	}
	.addressSearch{
		position:absolute;
		width: 45%;
		height: 60rpx;
		border: #BBBBBB solid 1px;
		display: inline-block;
		margin-left: 280rpx;
		margin-top:  24rpx;
	}
	.presentLocation{
		width:100%;
		height: 120rpx;
		border-bottom: #BBBBBB solid 1px;
	}
	.preLocaTitle{
		margin-left:10rpx;
		display:block;
		font-size:31rpx;
	}
	.preLocaName{
		line-height:60rpx;
		display:inline-block;
		font-size:31rpx;
		margin-left:100rpx;
	}
	.relocation{
		line-height:60rpx;
		display:inline-block;
		font-size:31rpx;
		float:right;
		color:#3F51B5;
		margin-right:10rpx;
	}
	.shippingAddress{
		width:100%;
		margin-top:10rpx;
		border-top: #BBBBBB solid 1px;
	}
	.shippingAddressTop{
		height:100rpx;
		border-bottom: #BBBBBB solid 1px;
	}
	.shipAddressTitle{
		line-height:100rpx;
		display:inline-block;
		margin-left:10rpx;
		font-size:31rpx;
	}
	.manageAddress{
		line-height:100rpx;
		display:inline-block;
		float:right;
		margin-right:10rpx;
		color:#3F51B5;
		font-size:31rpx;
	}
</style>
