<template>
	<view>
		<view class="Top">已自动选择最优方案,共节省x元,点击可修改</view>
		<view class="Nav">
			<view class="NavCh1" v-for="(item,index) in list" :key="index" @click="GotoAdjust">
				<view class="NavCh_Name_Msgs">
					<view class="Nav_Name">{{item.name}}</view>
					<view class="Nav_Msgs">{{item.msgs}}</view>
				</view>
				<view class="NavStatus">{{item.status}}</view>
				<view class="NavPrice">
					<view class="NavNewPrice">￥{{item.newPrice}}</view>
					<view class="NavOldPrice">￥{{item.oldPrice}}</view>
				</view>
				<view class="YouHuiPrice">-{{item.youhui}}</view>
			</view>
			<view class="gao" style="height: 180rpx;">
				
			</view>
		</view>
		<view class="Btns">确认</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[{
					name:'T恤,抹胸',
					msgs:'修复/洗护/特殊污渍',
					status:'已使用【优惠卡】',
					newPrice:28,
					oldPrice:3,
					youhui:24,
					id:1
				},{
					name:'T恤,抹胸',
					msgs:'修复/洗护/特殊污渍',
					status:'已使用【月卡】',
					newPrice:28,
					oldPrice:3,
					youhui:24,
					id:1
				},{
					name:'T恤,抹胸',
					msgs:'修复/洗护/特殊污渍',
					status:'已使用【优惠卡】',
					newPrice:28,
					oldPrice:3,
					youhui:24,
					id:1
				},{
					name:'T恤,抹胸',
					msgs:'修复/洗护/特殊污渍',
					status:'已使用【优惠卡】',
					newPrice:28,
					oldPrice:3,
					youhui:24,
					id:1
				},{
					name:'T恤,抹胸',
					msgs:'修复/洗护/特殊污渍',
					status:'已使用【月卡】',
					newPrice:28,
					oldPrice:3,
					youhui:24,
					id:1
				},{
					name:'T恤,抹胸',
					msgs:'修复/洗护/特殊污渍',
					status:'已使用【优惠卡】',
					newPrice:28,
					oldPrice:3,
					youhui:24,
					id:1
				},{
					name:'T恤,抹胸',
					msgs:'修复/洗护/特殊污渍',
					status:'已使用【优惠卡】',
					newPrice:28,
					oldPrice:3,
					youhui:24,
					id:1
				},{
					name:'T恤,抹胸',
					msgs:'修复/洗护/特殊污渍',
					status:'已使用【优惠卡】',
					newPrice:28,
					oldPrice:3,
					youhui:24,
					id:1
				}]
			}
		},
		methods: {
			GotoAdjust() {
				uni.navigateTo({
					url:'../../../shoppingcart/jieSuan/preferentialCart/adjustCart/adjustCart'
				})
			}
		}
	}
</script>

<style>
	.Top {
		width: 100%;
		height: 80rpx;
		background: rgba(209, 209, 209, 0.2);
		text-align: center;
		line-height: 80rpx;
		font-size: 24rpx;
	}
	.Nav {
		width: 100%;
		height: 100%;
		overflow: scroll;
	}
	.NavCh1 {
		position: relative;
		width: 100%;
		height: 200rpx;
		background: white;
		margin-top: 15rpx;
	}
	.NavCh1:nth-of-type(1) {
		margin-top: 0rpx;
	}
	.NavCh_Name_Msgs {
		position: absolute;
		top: 30rpx;
		left: 2%;
		width: 240rpx;
		height: 80rpx;
	}
	.Nav_Name {
		width: 100%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 36rpx;
		font-weight: bold;
	}
	.Nav_Msgs {
		width: 100%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 24rpx;
		
	}
	.NavStatus {
		position: absolute;
		bottom: 30rpx;
		left: 2%;
		width: 300rpx;
		height: 50rpx;
		color: #1482D1;
		font-size: 36rpx;
	}
	.NavPrice {
		position: absolute;
		top: 30rpx;
		right: 2%;
		width: 100rpx;
		height: 80rpx;
	}
	.NavNewPrice {
		width: 100%;
		height: 40rpx;
		font-size: 36rpx;
		font-weight: bold;
	}
	.NavOldPrice {
		width: 100%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 24rpx;
	}
	
	.YouHuiPrice {
		position: absolute;
		right: 2%;
		bottom: 30rpx;
		color: #0A98D5;
		font-size: 32rpx;
		line-height: 40rpx;
		height: 40rpx;
		width: 100rpx;
	}
	
	.Btns {
		position: fixed;
		bottom: 0rpx;
		left: 0rpx;
		height: 90rpx;
		width: 100%;
		text-align: center;
		line-height: 90rpx;
		color: white;
		background: #0A98D5;
		font-size: 34rpx;
		font-weight: bold;
	}
</style>
