<template>
	<view class="tall">
		<!-- 顶部展示 -->
		<view class="bukuanTop">
			<view class="TopStatus_Thank">
				<view class="TopStatus">等待补款中</view>
				<view class="TopThank">感谢您的使用</view>
			</view>
			<view class="TopBeiZhu">补款备注:因为有太多油污，特殊处理需补款</view>
			<view class="TopImgs">
				<view class="TopImgsName">补款图片</view>
				<view class="TopImgsAll">
					<image src="../../static/images/left.png" mode=""></image>
					<image src="../../static/images/1.jpg" mode=""></image>
					<image src="../../static/images/1.jpg" mode=""></image>
					<image src="../../static/images/1.jpg" mode=""></image>
					<image src="../../static/images/1.jpg" mode=""></image>
					<image src="../../static/images/jiantou.png" mode=""></image>
				</view>
				<view class="TopPrice">补款金额:10000元</view>
				<view class="TopTiShi">提示:若有其它需求请及时联系管家/配送员</view>
			</view>
		</view>
		<!-- 中部展示 -->
		<view class="BodyMsgs">
			<view class="Body_TopMsg">处理门店</view>
			<view class="Body_LittleMsgs">
				翡翠城店(NO.11000)
				<br>
				具体地址:翡翠城店
				<br>
				联系方式:12345678912
			</view>
		</view>
		<!-- 中下部展示信息-->
		<view class="Body_Bottom">
			<view class="Body_Bottom_Danhao_Time">
				<view class="Bottom_DanHao">配送订单:jsdj456413145645</view>
				<view class="Bottom_Time">2019-07-12 12:16</view>
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
					<view class="MoreMsgs_UseYouHui">使用优惠券</view>
					<view class="MoreMsgs_JianPrice">-28</view>
				</view>
			</view>
			<view class="Bottom_FuWuCount">
				<view class="FuWuCount_Name">共1次服务</view>
				<view class="FuWuCount_Pirce">实付￥3</view>
			</view>
		</view>
		<!-- 底部信息展示 -->
		<view class="Footer">
			<view class="True_Pirce">还需支付<view class="True_HowPrice">￥9</view></view>
			<view class="ZhiFu_Btn">去支付</view>
		</view>
	</view>
</template>

<script>
</script>

<style>
	.tall {
		width: 100%;
		height: 100%;
		background-color: white;
	}
	.bukuanTop {
		width: 96%;
		margin-left: 2%;
	}
	.TopStatus_Thank {
		width: 50%;
		height: 100rpx;
		margin-left: 25%;
		padding-top: 36rpx;
	}
	.TopStatus {
		width: 100%;
		height: 50rpx;
		line-height: 50rpx;
		text-align: center;
		font-size: 30rpx;
		font-weight: bold;
	}
	.TopThank {
		width: 100%;
		height: 40rpx;
		line-height: 40rpx;
		text-align: center;
		font-size: 20rpx;
		font-weight: bold;
	}
	.TopBeiZhu {
		width: 100%;
		height: 24rpx;
		line-height: 24rpx;
		font-size: 20rpx;
		margin-top: 10rpx;
	}
	.TopImgs {
		position: relative;
		width: 100%;
		height: 214rpx;
		margin-top: 10rpx;
		border-bottom: 1rpx solid #C7C6CD;
		
	}
	.TopImgsName {
		position: absolute;
		top: 15rpx;
		width: 132rpx;
		left: 0rpx;
		font-size: 20rpx;
	}
	.TopImgsAll {
		display: flex;
		justify-content: space-between;
		position: absolute;
		top: 0rpx;
		right: 0rpx;
		width: 540rpx;
		height: 130rpx;
		border: 1rpx solid black;
	}
	.TopImgsAll image {
		width: 70rpx;
		height: 100rpx;
	}
	.TopPrice {
		position: absolute;
		width: 100%;
		height: 30rpx;
		line-height: 30rpx;
		top: 138rpx;
		font-size: 20rpx;
	}
	.TopTiShi {
		position: absolute;
		bottom: 10rpx;
		width: 100%;
		height: 30rpx;
		line-height: 30rpx;
		font-size: 20rpx;
		margin-top: 12rpx;
	}
	/* body部分 */
	.BodyMsgs {
		width: 100%;
		height: 170rpx;
		margin-top: 10rpx;
		border-top: 1rpx solid #C7C6CD;
		border-bottom: 1rpx solid #C7C6CD;
	}
	
	.Body_TopMsg {
		width: 60%;
		height: 40rpx;
		font-size: 26rpx;
		margin-left: 2%;
	}
	.Body_LittleMsgs {
		width: 100%;
		height: 120rpx;
		line-height: 34rpx;
		font-size: 24rpx;
		margin-top: 20rpx;
		margin-left: 2%;
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
		height: 80rpx;
		border-bottom: 1rpx solid #C7C6CD;
		display: flex;
		justify-content: space-between;
	}
	.Bottom_DanHao {
		width: 400rpx;
		height: 80rpx;
		line-height: 80rpx;
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
		height: 68rpx;
		display: flex;
		border-bottom: 1rpx solid #C7C6CD;
		justify-content: space-between;
	}
	.MoreMsgs_UseYouHui {
		width: 200rpx;
		height: 50rpx;
		line-height: 50rpx;
		margin-left: 2%;
		font-size: 30rpx;
		font-weight: bold;
		color: #007AFF;
	}
	.MoreMsgs_JianPrice {
		width: 140rpx;
		height: 50rpx;
		line-height: 50rpx;
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
	.Footer {
		position: fixed;
		bottom: 0rpx;
		left: 0rpx;
		width: 100%;
		border-top: 1rpx solid #C7C6CD;
		height: 108rpx;
		display: flex;
		justify-content: space-between;
	}
	.True_Pirce {
		position: relative;
		height: 108rpx;
		width: 200rpx;
		font-size: 28rpx;
		line-height: 108rpx;
		margin-left: 2%;
	}
	.True_HowPrice {
		position: absolute;
		width: 98rpx;
		right: -4rpx;
		top: 0rpx;
		height: 108rpx;
		line-height: 112rpx;
		font-weight: bold;
		font-size: 34rpx;
	}
	
	.ZhiFu_Btn {
		background-color: #0000FF;
		color: white;
		width: 204rpx;
		font-size: 30rpx;
		font-weight: bold;
		line-height: 108rpx;
		text-align: center;
		height: 18rpx;
		height: 190rpx;
	}
</style>
