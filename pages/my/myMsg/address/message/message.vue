<template>
	<view>
		<view class="NavCh1" v-for="(item,index) in list" :key="index">
			<view class="NavChName">{{item.name}}</view>
			<view class="NavChTime">{{item.time}}</view>
			<view class="NavMsgs">{{item.msgs}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[{
					name:'您的订单已经处理完成',
					time:'2019-07-16  12:45',
					msgs:'白色的花瓣和对方数据的分布是大部分还是是对方均表示电话方便说不定就发',
					id:1
				},{
					name:'您已获得1张4.8折洗衣优惠券',
					time:'2019-07-16  12:45',
					msgs:'您已获得1张4.8折洗衣优惠券',
					id:2
				},{
					name:'充1000送500进行中',
					time:'2019-07-16  12:45',
					msgs:'充1000送500进行中',
					id:3
				}]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.NavCh1 {
		position: relative;
		width: 100%;
		min-height: 200rpx;
		border-bottom: 1rpx solid #B2B2B2;
	}
	.NavChName {
		position: absolute;
		top: 15rpx;
		left: 2%;
		width: 410rpx;
		overflow: hidden;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 30rpx;
		font-weight: bold;
	}
	.NavChTime {
		position: absolute;
		right: 2%;
		top: 15rpx;
		width: 300rpx;
		text-align: right;
		height: 40rpx;
		line-height: 40rpx;
		color: #C7C6CD;
		font-size: 24rpx;
	}
	.NavMsgs {
		position: absolute;
		top: 75rpx;
		left: 2%;
		width: 96%;
		height: auto;
		font-size: 30rpx;
		color: #C7C6CD;
		line-height: 50rpx;
		/* bottom: -30rpx; */
		/* padding-bottom: 30rpx; */
	}
</style>
