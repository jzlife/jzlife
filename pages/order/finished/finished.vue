<template>
	<view class="tall">
		<view class="Nav">
			<view class="TopNumber_Status">
				<view class="TopNumber">配送订单:xdjd1543548723</view>
				<view class="TopStatus">已完成</view>
			</view>
			<view class="TopAllMsgs">
				<view class="TopName_Msgs">
					<view class="TopName">翡翠城店(NO.1000)</view>
					<view class="TopN_Msgs">衣物清洁等,共1次服务</view>
				</view>
				<view class="Top_Time">2019-07-12 12:43</view>
				<view class="Top_Price">￥10</view>
				<view class="TopBtns">
					<view class="Btns_Again">再来一单</view>
					<view class="Btns_Talk">评价</view>
				</view>
			</view>
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

		}
	}
</script>

<style>
	.tall {
		width: 100%;
		height: 100%;
	}
	.Nav {
		width: 100%;
		height: 240rpx;
		border: 1rxp solid black;
		margin-top: 10rpx;
	}
	.TopNumber_Status {
		width: 96%;
		height: 60rpx;
		border: 1rpx solid red;
		display: flex;
		justify-content: space-between;
	}
	.TopNumber {
		width: 300rpx;
		height: 60rpx;
		line-height: 60rpx;
		font-size: 24rpx;
		color: #C7C6CD;
	}
	.TopStatus {
		width: 300rpx;
		height: 60rpx;
		line-height: 60rpx;
		font-size: 24rpx;
		color: #C7C6CD;
		text-align: right;
	}
	.TopAllMsgs {
		position: relative;
		width: 96%;
		height: 180rpx;
		margin-left: 2%;
		border: 1rpx solid black;
	}
	.TopName_Msgs {
		position: absolute;
		top: 10rpx;
		left: 0rpx;
		width: 360rpx;
		height: 80rpx;
		border: 1rpx solid black;
	}
	.TopName {
		width: 100%;
		height: 50rpx;
		line-height: 50rpx;
		font-size: 32rpx;
		font-weight: bold;
	}
	.TopN_Msgs {
		width: 100%;
		height: 30rpx;
		line-height: 30rpx;
		font-size: 24rpx;
		font-weight: bold;
	}
	.Top_Time {
		position: absolute;
		top: 10rpx;
		right: 0rpx;
		height: 30rpx;
		width: 300rpx;
		color: #C7C6CD;
		text-align: right;
		font-size: 24rpx;
	}
	.Top_Price {
		position: absolute;
		top: 250rpx;
		left: 0rpx;
		width: 100rpx;
		height: 60rpx;
		line-height: 660rpx;
		font-size: 32rpx;
		font-weight: bold;
	}
	.TopBtns {
		position: absolute;
		top: 250rpx;
		right: 0rpx;
		width: 300rpx;
		height: 60rpx;
		border: 1rpx solid black;
		display: flex;
		justify-content: space-between;
	}
	.Btns_Again {
		width: 150rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		font-size: 32rpx;
		border: 1rpx solid #C7C6CD;
	}
	.Btns_Talk {
		width: 120rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		font-size: 32rpx;
		border: 1rpx solid #C7C6CD;
	}
</style>
