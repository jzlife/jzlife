<template>
	<view class="tall">
		<view class="TopImgs">
			<image src="../../static/images/1.jpg" mode=""></image>
		</view>
		<view class="NavMsgs">
			<view class="NavCh1" v-for="(item,index) in list" :key="index">
				<image @click="chosedGoods(item.id, index)" class="chooseGoods" :src="item.chosed?'../../static/images/chosed.png':'../../static/images/addN.png'" mode=""></image>
				<!-- <image src="../../static/images/chosed.png" mode=""></image> -->
				<view class="GoodsTitle_Msgs" @click="xiangqing(item.id)">
					<view class="GoodsTitle">{{item.name}}</view>
					<view class="GoodsMsgs">{{item.msgs}}</view>
				</view>
				<view class="GoodsPrice" @click="xiangqing(item.id)">
					<view class="newPrice">￥{{item.newPrice}}</view>
					<view class="oldPrice">￥{{item.oldPrice}}</view>
				</view>
				<view class="addCounts">
					<image class="sub" src="../../static/images/subN.png" mode="" @click="subCount(item.id,index)"></image>
					<view class="Counts">{{item.counts}}</view>
					<image class="add" src="../../static/images/addN.png" mode="" @click="addCount(item.id,index)"></image>
				</view>
			</view>
			<view class="gao" style="height: 200rpx;">

			</view>
		</view>
		<view class="footer">
			<view class="footerCount">应付合计:￥{{priceAll()}}</view>
			<view class="footerBtn" @click="jiesuan">结算</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
					name: 'T恤,抹胸',
					msgs: '养护/修复/特殊污渍',
					newPrice: 19.34,
					oldPrice: 27.98,
					counts: 1, //商品数量
					id: 1,
					chosed:false
				}, {
					name: 'T恤,抹胸',
					msgs: '养护/修复/特殊污渍',
					newPrice: 19.34,
					oldPrice: 27.98,
					counts: 1, //商品数量
					id: 2,
					chosed:false
				}, {
					name: 'T恤,抹胸',
					msgs: '养护/修复/特殊污渍',
					newPrice: 19.34,
					oldPrice: 27.98,
					counts: 1, //商品数量
					id: 3,
					chosed:false
				}, {
					name: 'T恤,抹胸',
					msgs: '养护/修复/特殊污渍',
					newPrice: 19.34,
					oldPrice: 27.98,
					counts: 1, //商品数量
					id: 4,
					chosed:false
				}, {
					name: 'T恤,抹胸',
					msgs: '养护/修复/特殊污渍',
					newPrice: 19.34,
					oldPrice: 27.98,
					counts: 1, //商品数量
					id: 5,
					chosed:false
				}, {
					name: 'T恤,抹胸',
					msgs: '养护/修复/特殊污渍',
					newPrice: 19.34,
					oldPrice: 27.98,
					counts: 1, //商品数量
					id: 6,
					chosed:false
				}, {
					name: 'T恤,抹胸',
					msgs: '养护/修复/特殊污渍',
					newPrice: 19.34,
					oldPrice: 27.98,
					counts: 0, //商品数量
					id: 7,
					chosed:false
				}, {
					name: 'T恤,抹胸',
					msgs: '养护/修复/特殊污渍',
					newPrice: 19.34,
					oldPrice: 27.98,
					counts: 1, //商品数量
					id: 8,
					chosed:false
				}],
				price:0,   //所有价格
			}
		},
		methods: {
			subCount(id, index) {
				var id = id
				var index = index
				if (index + 1 == id) {
					this.list[index].counts--
					if (this.list[index].counts <= 0) {
						this.list[index].counts = 0
					}
				}
			},
			addCount(id, index) {
				var id = id
				var index = index
				if (index + 1 == id) {
					this.list[index].counts++
				}
			},
			priceAll() {
				var priceAll = 0
				this.list.forEach(function(item) {
					if(item.chosed) {
						priceAll += item.counts * item.newPrice
					}
				})
				this.price = priceAll.toFixed(2)
				return priceAll.toFixed(2)
			},
			// 勾选商品
			chosedGoods(id,index) {
				var id = id
				var index = index
				if(index+1 == id) {
					this.list[index].chosed = !this.list[index].chosed
				}
			},
			jiesuan() {
				uni.showModal({
					title:'结算加载',
					showCancel:false,
					content:'一共需要结算'+this.price+'元'
				})
			},
			xiangqing(e) {
				uni.navigateTo({
					url:'../shoppingcart/jieSuan/jieSuan'
				})
			}
		}

	}
</script>

<style>
	.TopImgs {
		width: 100%;
		height: 140rpx;
		overflow: hidden;
	}

	.TopImgs image {
		width: 100%;
		height: 100%;
	}

	.NavMsgs {
		width: 100%;
		height: 1014rpx;
		overflow: scroll;
		/* margin-bottom: 100rpx; */
	}

	.NavCh1 {
		position: relative;
		width: 96%;
		height: 160rpx;
		border-top: 1rpx solid #C8C7CC;
		border-bottom: 1rpx solid #C8C7CC;
		margin-top: 10rpx;
		margin-left: 2%;
	}

	.chooseGoods {
		position: absolute;
		width: 60rpx;
		height: 60rpx;
		top: 45rpx;
		left: 0rpx;
		border-radius: 50%;
	}

	.GoodsTitle_Msgs {
		position: absolute;
		width: 252rpx;
		height: 100rpx;
		left: 80rpx;
		top: 30rpx;
	}

	.GoodsTitle {
		width: 100%;
		height: 60rpx;
		line-height: 60rpx;
		font-size: 32rpx;
		font-weight: bold;
	}

	.GoodsMsgs {
		width: 100%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 26rpx;
	}

	.GoodsPrice {
		position: absolute;
		right: 174rpx;
		height: 100rpx;
		top: 30rpx;
		width: 140rpx;
	}

	.newPrice {
		width: 100%;
		height: 70rpx;
		color: red;
		font-size: 32rpx;
		line-height: 70rpx;
		text-align: right;
		font-weight: bold;
	}

	.oldPrice {
		width: 100%;
		height: 30rpx;
		line-height: 30rpx;
		text-align: right;
		text-decoration: line-through;
		font-size: 22rpx;
	}

	.addCounts {
		position: absolute;
		right: 10rpx;
		width: 128rpx;
		height: 50rpx;
		top: 50rpx;
		display: flex;
		justify-content: space-between;
	}

	.sub,
	.add {
		width: 50rpx;
		height: 50rpx;
	}

	.Counts {
		width: 30rpx;
		height: 50rpx;
		line-height: 50rpx;
		text-align: center;
		font-size: 24rpx;
	}

	.footer {
		position: fixed;
		bottom: 96rpx;
		left: 0rpx;
		width: 100%;
		background-color: white;
		height: 132rpx;
		display: flex;
		justify-content: space-between;
	}

	.footerCount {
		width: 376rpx;
		height: 132rpx;
		line-height: 132rpx;
		font-size: 34rpx;
		margin-left: 12rpx;
	}

	.footerBtn {
		width: 257rpx;
		height: 132rpx;
		line-height: 132rpx;
		text-align: center;
		font-size: 34rpx;
		font-weight: bold;
		color: white;
		background-color: #007AFF;
	}
</style>
