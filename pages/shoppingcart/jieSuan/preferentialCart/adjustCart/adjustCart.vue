<template>
	<view>
		<view class="Top">
			<text>可用x张</text>
		</view>
		<view class="Nav">
			<view class="NavTop">
				<view class="NavTop_Name">T恤优惠券
					<view class="NavTopStatus">已占用</view>
				</view>
				<view class="NavTime">有效期至2019-07-12</view>
			</view>
			<view class="NavR">
				<view class="NavRuleName">
					使用规则
					<image @click="showMores" :src="showMore?'../../../../../static/images/down.png':'../../../../../static/images/right.png'" mode=""></image>
				</view>
				<!-- <input type="checkbox" id="B" class="Btns" value="" /> -->
				<label class="checkbox">
					<checkbox value="" checked="true" />
				</label>
				<!-- <label class="radio">
					<radio value="" />
				</label> -->
			</view>
			<view class="showMore" v-show="showMore">
				hahahhahahhah哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showMore:false,
			}
		},
		methods: {
			showMores(){
				this.showMore = !this.showMore
			}
		}
	}
</script>

<style>
	.Top {
		width: 100%;
		height: 80rpx;
		background: rgba(1, 1, 1, .2);
		line-height: 80rpx;
		font-size: 24rpx;
	}

	.Top text {
		margin-top: 0rpx;
		margin-left: 2%;
	}

	.Nav {
		width: 100%;
		height: 100%;
	}

	.NavTop {
		width: 100%;
		height: 120rpx;
		background-color: white;
		border-top: 1rpx solid #BBBBBB;
		border-bottom: 1rpx solid #BBBBBB;
	}

	.NavTop_Name {
		position: relative;
		margin-left: 2%;
		margin-top: 20rpx;
		height: 40rpx;
		width: 254rpx;
		line-height: 40rpx;
		font-size: 30rpx;
		font-weight: bold;
	}

	.NavTopStatus {
		position: absolute;
		top: 0rpx;
		right: 0rpx;
		width: 100rpx;
		color: #0A98D5;
		height: 40rpx;
		line-height: 40rpx;
	}

	.NavTime {
		position: absolute;
		height: 40rpx;
		left: 2%;
		width: 400rpx;
		line-height: 40rpx;
		font-size: 24rpx;
		color: #BBBBBB;
	}

	.NavR {
		border-bottom: 1rpx solid #BBBBBB;
		height: 60rpx;
		width: 100%;
		display: flex;
		background: white;
		justify-content: space-between;
	}

	.NavRuleName {
		position: relative;
		margin-top: 0rpx;
		margin-left: 2%;
		width: 160rpx;
		height: 60rpx;
		font-size: 30rpx;
		font-weight: bold;
	}

	.NavRuleName image {
		position: absolute;
		top: 10rpx;
		right: 0rpx;
		width: 40rpx;
		height: 40rpx;
	}
	.showMore {
		width: 96%;
		min-height: 200rpx;
		background: white;
		font-size: 32rpx;
		line-height: 40rpx;
		margin-left: 2%;
		text-spacing: 30rpx;
		/* color: #888888; */
		
	}

</style>
