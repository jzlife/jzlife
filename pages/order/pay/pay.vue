<template>
	<view class="tall">
		<radio-group @change="chooseClass">
			<radio value="wx" class="Nav">
				<image class="NavImgs" src="../../../static/images/wx.png" mode=""></image>
				<view class="NavName">微信支付</view>
			</radio>
			<radio value="yue" class="Nav">
				<image class="NavImgs" src="../../../static/images/yue.png" mode=""></image>
				<view class="NavName">余额支付</view>
				<view class="NavTuijian">
					<image src="../../../static/images/tuijian.png" mode=""></image>
				</view>
			</radio>
			<radio value="zfb" class="Nav">
				<image class="NavImgs" src="../../../static/images/zfb.png" mode=""></image>
				<view class="NavName">支付宝支付</view>
			</radio>
		</radio-group>
		<view class="Zhifu">
			<!-- <input type="radio" id="Zhifuinput" value="" /> -->
			<!-- <label class="checkbox" id="Zhifuinput">
				<checkbox value="" />
			</label> -->
			<label class="radio" id="Zhifuinput">
				<radio value="" />
			</label>
			<!-- <Radio class="checkbox"></Radio> -->
			<view class="aboutMsgs">我已阅读并同意
				<text>支付协议</text>
			</view>
			<view class="Btn" @click="btns">付款</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				cClass:''
			}
		},
		methods: {
			Status(e) {
				console.log(e)
			},
			chooseClass(e){
				this.cClass = e.detail.value
			},
			btns() {
				console.log(this.cClass)
			}
		}
	}
</script>

<style>
	.tall {
		width: 100%;
		height: 100%;
	}

	.Nav {
		position: relative;
		width: 100%;
		height: 130rpx;
		padding-left: 650rpx;
		line-height: 130rpx;
		border: 1rpx solid #C7C6CD;
	}

	.NavImgs {
		position: absolute;
		width: 60rpx;
		height: 60rpx;
		top: 35rpx;
		left: 46rpx;
	}
	
	.NavName {
		position: absolute;
		width: 158rpx;
		height: 80rpx;
		font-size: 30rpx;
		line-height: 80rpx;
		top: 25rpx;
		left: 128rpx;
	}

	.NavTuijian {
		position: absolute;
		height: 80rpx;
		width: 150rpx;
		line-height: 80rpx;
		color: red;
		left: 262rpx;
		top: 25rpx;
	}

	.NavTuijian image {
		position: absolute;
		top: 15rpx;
		left: 0rpx;
		width: 50rpx;
		height: 50rpx;
	}

	#NavInput {
		position: absolute;
		top: 40rpx;
		right: 20rpx;
		width: 50rpx;
		height: 50rpx;
		/* border: none; */
		/* border-radius: 50%; */
	}

	.Zhifu {
		position: relative;
		width: 100%;
		height: 130rpx;
		border: 1rpx solid #C7C6CD;
	}

	#Zhifuinput {
		position: absolute;
		width: 40rpx;
		height: 40rpx;
		top: 2rpx;
		left: 30rpx;
	}

	.aboutMsgs {
		position: absolute;
		top: 18rpx;
		font-size: 30rpx;
		left: 100rpx;
		width: 354rpx;
		height: 50rpx;
	}

	.aboutMsgs text {
		color: #0A98D5;
	}

	.Btn {
		position: absolute;
		width: 200rpx;
		height: 50rpx;
		bottom: 8rpx;
		left: 50%;
		transform: translateX(-50%);
		border: 1rpx solid #C7C6CD;
		border-radius: 10rpx;
		text-align: center;
		line-height: 50rpx;
		font-size: 30rpx;
	}
</style>
