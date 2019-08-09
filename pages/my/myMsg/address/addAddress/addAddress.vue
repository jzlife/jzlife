<template>
	<view>
		<view class="NavCh">
			<view class="NavChMsgs1">
				联系人 <input type="text" value="" placeholder="用户取件时对您的称呼" />
			</view>
		</view>
		<view class="NavCh">
			<view class="NavChMsgs2">性别
				<radio-group class="ChooseSex">
					<radio>先生</radio>
					<radio>女士</radio>
				</radio-group>
			</view>
		</view>
		<view class="NavCh">
			<view class="NavChMsgs1">
				手机号 <input type="text" value="" placeholder="133355987" />
			</view>
		</view>
		<view class="NavCh address">
			<view class="NavChMsgs3">
				地址
				<view class="NavAddress">希顿国际广场C座 天府大道666号</view>
				<image src="../../../../../static/images/jiantou.png" mode=""></image>
			</view>
		</view>
		<view class="NavCh">
			<view class="NavChMsgs1">
				门牌号 <input type="text" value="" placeholder="2907" />
			</view>
		</view>
		<view class="NavCh">
			<view class="NavChMsgs4">
				标签
				<view class="ChMsgs4More">
					<view class="Ch4MsgsCh">家</view>
					<view class="Ch4MsgsCh">公司</view>
					<view class="Ch4MsgsCh">学校</view>
					<view class="Ch4MsgsCh">自定义</view>
					<!-- <button open-type="launchApp" class="Ch4MsgsCh">学校</button> -->
					<!-- <button open-type="getPhoneNumber" class="Ch4MsgsCh">自定义</button> -->
				</view>
			</view>
		</view>
		<view class="moren">
			<label class="checkbox">
				<checkbox value="" checked="true" />
				<view class="morenAddress">设为默认地址</view>
			</label>
		</view>
		<view class="Btns">
			<view class="btnLeft">删除</view>
			<view class="btnRight">保存</view>
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
	.NavCh {
		width: 100%;
		height: 100rpx;
		border-bottom: 1rpx solid #B2B2B2;
	}

	.NavChMsgs1,
	.NavChMsgs2,
	.NavChMsgs3,
	.NavChMsgs4 {
		width: 96%;
		margin-left: 2%;
		height: 100rpx;
		border-bottom: 1rpx solid #B2B2B2;
		line-height: 100rpx;
		font-size: 24rpx;
	}

	.NavChMsgs1,
	.NavChMsgs2 {
		position: relative;
	}

	.NavChMsgs1 input {
		position: absolute;
		left: 120rpx;
		height: 40rpx;
		top: 30rpx;
		width: 400rpx;
		border: 1rpx solid #808080;
	}

	.ChooseSex {
		position: absolute;
		width: 300rpx;
		height: 40rpx;
		display: flex;
		justify-content: space-between;
		top: 0rpx;
		/* border: 1rpx solid #000000; */
		left: 120rpx;
	}


	.NavAddress {
		position: absolute;
		left: 120rpx;
		font-size: 24rpx;
		width: 450rpx;
		height: 40rpx;
		top: 0rpx;

	}

	.address {
		position: relative;
	}

	.address image {
		position: absolute;
		right: 10rpx;
		width: 40rpx;
		height: 40rpx;
		top: 30rpx;
	}

	.NavChMsgs4 {
		position: relative;
	}

	.ChMsgs4More {
		position: absolute;
		width: 80%;
		left: 120rpx;
		height: 60rpx;
		top: 20rpx;
		display: flex;
		justify-content: space-between;
	}

	.Ch4MsgsCh {
		width: 22%;
		height: 100%;
		line-height: 60rpx;
		border: 1rpx solid #B2B2B2;
		text-align: center;
		font-size: 24rpx;
	}

	.moren {
		position: relative;
		width: 100%;
		height: 60rpx;
	}

	.checkbox {
		position: absolute;
		left: 2%;
		top: 10rpx;

	}

	.morenAddress {
		font-size: 24rpx;
		position: absolute;
		left: 70rpx;
		top: 0rpx;
		width: 300rpx;
		height: 60rpx;
		line-height: 60rpx;
	}
	
	.Btns {
		position: fixed;
		width: 70%;
		height: 60rpx;
		left: 15%;
		bottom: 60rpx;
		display: flex;
		justify-content: space-between;
	}
	.btnLeft, .btnRight {
		width: 40%;
		height: 60rpx;
		text-align: center;
		font-size: 24rpx;
		line-height: 60rpx;
	}
	.btnLeft {
		border: 1rpx solid #B2B2B2;
		color: #000000;
	}
	.btnRight {
		background-color: #0A98D5;
		color: white;
		
	}
</style>
