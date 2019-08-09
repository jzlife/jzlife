<template>
	<view>
		<view class="Top">
			<view class="TopAddress">
				<view class="TAddress">
					<image src="../../../static/images/lat.png" mode=""></image>
					<view class="TaddressName">新希望国际A座1002号</view>
				</view>
				<view class="TelName">
					<image src="../../../static/images/tel.png" mode="" style="width: 40rpx;height: 40rpx;"></image>
					<view class="TeldetialMsgs">13646487645 名字</view>
				</view>
				<image class="goToAddress" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="TMoreMsgs">此订单为门店附近订单,由管家配送,免除配送费用</view>
			<view class="TTimes">
				<view class="Tremind">取件时间</view>
				<view class="Tdetail">推荐时间</view>
				<view class="TrecommendTime">
					今天15:00-15:30
					<image src="../../../static/images/jiantou.png" mode=""></image>
				</view>
			</view>
		</view>
		<!-- body -->
		<view class="Body_Bottom">
			<view class="Body_Bottom_Danhao_Time">
				<view class="Bottom_DanHao">订单信息</view>
				<!-- <view class="Bottom_Time">2019-07-12 12:16</view> -->
			</view>
			<view class="Body_Bottom_MoreMsg">
				<view class="MoreMsgs_Ch1">
					<view class="MoreMsgsCh1_Name">T恤,抹胸等</view>
					<view class="MoreMsgs_Count">x1</view>
					<view class="MoreMsgs_Price">￥28</view>
				</view>
				<view class="MoreMsgs_Ch1">
					<view class="MoreMsgsCh1_Name">T恤,抹胸等</view>
					<view class="MoreMsgs_Count">x1</view>
					<view class="MoreMsgs_Price">￥28</view>
				</view>
				<view class="MoreMsgs_Ch1">
					<view class="MoreMsgsCh1_Name">T恤,抹胸等</view>
					<view class="MoreMsgs_Count">x1</view>
					<view class="MoreMsgs_Price">￥28</view>
				</view>
				<view class="MoreMsgs_YouHui">
					<view class="MoreMsgs_UseYouHui">配送费</view>
					<view class="MoreMsgs_JianPrice">免费</view>
				</view>
			</view>
			<view class="Bottom_FuWuCount">
				<view class="FuWuCount_Name"></view>
				<view class="FuWuCount_Pirce">合计￥3</view>
			</view>
		</view>
		<!-- footer -->
		<view class="Footer">
			<view class="FooterCh1" @click="GoFuWu">
				<view class="FooterCh1_Name">使用服务卡</view>
				<view class="FooterCh1_Pirce">
					-￥25
				</view>
				<image class="GotoXiangQing" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="FooterCh1">
				<view class="FooterCh1_Name">使用优惠券</view>
				<view class="FooterCh1_Pirce">
					-￥25
				</view>
				<image class="GotoXiangQing" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
			<view class="FooterCh1">
				<view class="FooterCh1_Name">支付方式</view>
				<image class="QianBao" src="../../../static/images/dollar.png" mode=""></image>
				<view class="FooterCh1_Pirce">
					余额
				</view>
				<image class="GotoXiangQing" src="../../../static/images/jiantou.png" mode=""></image>
			</view>
		</view>
		<view class="FooterBtn">
			<view class="FooterPrice">
				<view class="FNewPrice">还需支付
					<text>￥9</text>
				</view>
				<view class="FOldPrcie">已抵扣￥24</view>
			</view>
			<view class="ZhiFuBtn">去支付</view>
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
			GoFuWu() {
				uni.navigateTo({
					url:'../../shoppingcart/jieSuan/preferentialCart/preferentialCart'
				})
			}
		}
	}
</script>

<style>
	.Top {
		width: 100%;
		height: 345rpx;
	}

	.TopAddress {
		position: relative;
		height: 152rpx;
		width: 96%;
		margin-left: 2%;
	}

	.TAddress {
		position: absolute;
		top: 40rpx;
		height: 40rpx;
		width: 420rpx;
	}

	.TAddress image {
		position: absolute;
		top: 0rpx;
		left: 0rpx;
		height: 40rpx;
		width: 40rpx;
	}

	.TaddressName,
	.TeldetialMsgs {
		position: absolute;
		top: 0rpx;
		left: 60rpx;
		font-size: 26rpx;
		height: 40rpx;
		line-height: 40rpx;
	}

	.TelName {
		position: absolute;
		bottom: 32rpx;
		height: 30rpx;
		line-height: 30rpx;
		width: 420rpx;
		font-size: 20rpx;
	}

	.TelName image {
		position: absolute;
		top: 0rpx;
		left: 0rpx;
		height: 30rpx;
		width: 30rpx;
	}

	.goToAddress {
		position: absolute;
		right: 10rpx;
		top: 50rpx;
		height: 52rpx;
		width: 52rpx;
	}

	.TMoreMsgs {
		width: 100%;
		height: 45rpx;
		line-height: 45rpx;
		text-align: center;
		color: #1482D1;
		font-size: 24rpx;
		border-top: 1rpx solid #BBBBBB;
		border-bottom: 1rpx solid #BBBBBB;
	}

	.TTimes {
		position: relative;
		width: 96%;
		height: 134rpx;
		margin-top: 10rpx;
	}

	.Tremind {
		position: absolute;
		top: 10rpx;
		width: 120rpx;
		height: 20rpx;
		margin-left: 2%;
		line-height: 20rpx;
		font-size: 24rpx;
		font-weight: bold;
	}

	.Tdetail {
		position: absolute;
		top: 40rpx;
		width: 200rpx;
		margin-left: 2%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 34rpx;
	}

	.TrecommendTime {
		position: absolute;
		top: 40rpx;
		right: 0rpx;
		width: 218rpx;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 20rpx;
	}

	.TrecommendTime image {
		position: absolute;
		top: 0rpx;
		right: 0rpx;
		width: 40rpx;
		height: 40rpx;
	}

	/* 中下部展示 */
	.Body_Bottom {
		width: 100%;
		height: 372rpx;
		border: 1rpx solid #C7C6CD;
		margin-top: 10rpx;
	}

	.Body_Bottom_Danhao_Time {
		width: 100%;
		height: 40rpx;
		border-bottom: 1rpx solid #C7C6CD;
		display: flex;
		justify-content: space-between;
	}

	.Bottom_DanHao {
		width: 400rpx;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 24rpx;
		margin-left: 2%;
	}

	.Bottom_Time {
		width: 300rpx;
		height: 80rpx;
		line-height: 80rpx;
		font-size: 24rpx;
		text-align: right;
		margin-right: 2%;

	}

	.Body_LittleMsg {
		width: 250rpx;
		height: 80rpx;
		line-height: 80rpx;
		text-align: right;
		font-size: 22rpx;
	}

	.Body_Bottom_MoreMsg {
		width: 100%;
	}

	.MoreMsgs_Ch1 {
		position: relative;
		width: 100%;
		height: 36rpx;
		line-height: 52rpx;
		margin-top: 12rpx;
	}

	.MoreMsgsCh1_Name {
		position: absolute;
		width: 250rpx;
		height: 36rpx;
		line-height: 36rpx;
		font-size: 30rpx;
		font-weight: bold;
		top: 0rpx;
		left: 2%;
	}

	.MoreMsgs_Count {
		position: absolute;
		top: 0rpx;
		left: 554rpx;
		width: 60rpx;
		height: 36rpx;
		line-height: 36rpx;
		font-size: 22rpx;
		text-align: center;
	}

	.MoreMsgs_Price {
		position: absolute;
		top: 0rpx;
		right: 0rpx;
		height: 36rpx;
		line-height: 36rpx;
		font-size: 30rpx;
		width: 80rpx;
		font-weight: bold;
	}

	.MoreMsgs_YouHui {
		width: 100%;
		height: 98rpx;
		display: flex;
		border-bottom: 1rpx solid #C7C6CD;
		justify-content: space-between;
	}

	.MoreMsgs_UseYouHui {
		width: 200rpx;
		height: 98rpx;
		line-height: 98rpx;
		margin-left: 2%;
		font-size: 30rpx;
		font-weight: bold;
		color: #007AFF;
	}

	.MoreMsgs_JianPrice {
		width: 140rpx;
		height: 98rpx;
		line-height: 98rpx;
		text-align: right;
		margin-right: 2%;
		font-size: 30rpx;
		color: #007AFF;
	}

	.Bottom_FuWuCount {
		width: 96%;
		height: 70rpx;
		display: flex;
		margin-left: 2%;
		justify-content: space-between;
	}

	.FuWuCount_Name {
		width: 300rpx;
		height: 70rpx;
		line-height: 70rpx;
		font-size: 22rpx;
	}

	.FuWuCount_Pirce {
		width: 200rpx;
		text-align: right;
		font-size: 30rpx;
		height: 70rpx;
		line-height: 70rpx;
	}

	/* footer */
	.Footer {
		width: 100%;
		height: 288rpx;
		margin-top: 10rpx;
	}

	.FooterCh1 {
		position: relative;
		width: 100%;
		height: 80rpx;
		border-top: 1rpx solid #BBBBBB;
	}

	.FooterCh1_Name {
		position: absolute;
		top: 10rpx;
		height: 60rpx;
		left: 2%;
		font-size: 24rpx;
		line-height: 60rpx;
	}

	.FooterCh1_Pirce {
		position: absolute;
		top: 10rpx;
		right: 80rpx;
		height: 60rpx;
		font-size: 24rpx;
		line-height: 60rpx;
		width: 80rpx;
		text-align: right;
	}

	.GotoXiangQing {
		position: absolute;
		right: 2%;
		width: 60rpx;
		height: 60rpx;
		top: 10rpx;
	}

	.QianBao {
		position: absolute;
		top: 10rpx;
		width: 60rpx;
		height: 60rpx;
		right: 140rpx;
	}
	/* 底部支付按钮 */
	.FooterBtn {
		position: fixed;
		bottom: 0rpx;
		left: 0rpx;
		width: 100%;
		height: 120rpx;
		border-top: 1rpx solid #BBBBBB;
		display: flex;
		justify-content: space-between;
	}
	.FooterPrice {
		width: 216rpx;
		height: 120rpx;
		margin-left: 2%;
	}
	.FNewPrice {
		width: 100%;
		height: 50rpx;
		margin-top: 20rpx;
		font-size: 24rpx;
		line-height: 50rpx;
	}
	.FNewPrice text {
		width: 70rpx;
		height: 50rpx;
		font-size: 36rpx;
		font-weight: bold;
		line-height:50rpx;
	}
	.FOldPrcie {
		width: 100%;
		height: 50rpx;
		line-height: 50rpx;
		font-size: 24rpx;
		margin-bottom: 10rpx;
	}
	.ZhiFuBtn {
		width: 190rpx;
		height: 100%;
		font-weight: bold;
		font-size: 36rpx;
		color: white;
		background: #0A98D5;
		text-align: center;
		line-height: 120rpx;
	}
</style>
