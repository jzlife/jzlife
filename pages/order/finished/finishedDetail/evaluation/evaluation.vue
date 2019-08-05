<template>
	<view class="tall">
		<view class="Nav">
			<view class="GS">
				<view class="Goods" v-show="!showSad">
					<image src="../../../../../static/images/weixiao.png" mode=""></image>
				</view>
				<view :class="showSad?'Sadshow':'Sad'" @click="SadTask(showSad)">
					<image src="../../../../../static/images/sad.png" mode=""></image>
				</view>
			</view>
			<view class="SadMsg" v-show="showSad">
				<view class="SadMsgCh1">
					<!-- <textarea class="SadCh1" value="" placeholder="" /> -->
					<input class="SadCh1" type="text" value="" />
					<image src="../../../../../static/images/add.png" mode=""></image>
				</view>
				<view class="SadMsgCh1">
					<input class="SadCh1" type="text" value="" />
					<image src="../../../../../static/images/add.png" mode=""></image>
				</view>
				<view class="SadMsgCh1">
					<input class="SadCh1" type="text" value="" />
					<image src="../../../../../static/images/add.png" mode=""></image>
				</view>
				<view class="SadMsgCh1">
					<input class="SadCh1" type="text" value="" />
					<image src="../../../../../static/images/add.png" mode=""></image>
				</view>
				<view class="SadMsgCh1">
					<input class="SadCh1" type="text" value="" />
					<image src="../../../../../static/images/add.png" mode=""></image>
				</view>
			</view>
			<textarea class="Nav_Msgs" value="" placeholder="请输入评价内容(可不填)" />
			<view class="Btns" @click="upSugestion(showSad)">提交</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showSad:false
			}
		},
		methods: {
			// 差评页面
			SadTask(e){
				this.showSad = !this.showSad
			},
			// 提交评价
			upSugestion(e){
				if(e == true) {
					uni.showModal({
						title:'极致生活',
						content:'感谢您的中肯评价,我们将及时为您查证和处理。为您带来的不便敬请谅解',
						showCancel:false
					})
				}
			}
		}
	}
</script>

<style>
	.tall {
		width: 100%;
		height: 100%;
		overflow: hidden;
	}
	.Nav {
		/* position: relative; */
		width: 100%;
		height: auto;
		margin-top: 90rpx;
	}
	.GS {
		width: 60%;
		margin-left: 20%;
		height: 80rpx;
		/* border: 1rpx solid black; */
		display: flex;
		justify-content: space-between;
	}
	.Goods,.Sad {
		/* position: absolute; */
		width: 80rpx;
		height: 80rpx;
		
	}
	.Sadshow {
		position: absolute;
		width: 80rpx;
		height: 80rpx;
		left: 50%;
		transform: translateX(-50%);
	}
	.Goods image,.Sadshow image,.Sad image {
		width: 100%;
		height: 100%;
	}
	.Sad {
		/* position: absolute; */
		width: 80rpx;
		height: 80rpx;
	}
	.Nav_Msgs {
		/* position: absolute; */
		margin-top: 30rpx;
		margin-left: 5%;
		width: 90%;
		height: 280rpx;
		border: 1rpx solid #999999;
		color: #3C3E49;
	}
	.Btns {
		width: 90%;
		height: 74rpx;
		border: 1rpx solid #999999;
		/* position: absolute; */
		margin-top: 30rpx;
		margin-left: 5%;
		font-size: 30rpx;
		text-align: center;
		line-height: 74rpx;
		color: #2C405A;
	}
	.SadMsg {
		margin-top: 30rpx;
		width: 80%;
		height: 484rpx;
		margin-left: 12%;
		/* border: 1rpx solid black; */
	}
	.SadMsgCh1 {
		width: 100%;
		height: 86rpx;
		/* border: 1rpx solid red; */
		display: flex;
		justify-content: space-between;
		margin-top: 10rpx;
	}
	.SadCh1 {
		height: 86rpx;
		width: 520rpx;
		border: #000000;
		font-size: 30rpx;
		border: 1rpx solid #7A7E83;
		color: #3C3E49;
	}
	.SadMsgCh1 image {
		width: 50rpx;
		height: 50rpx;
		margin-top: 18rpx;
	}
</style>
