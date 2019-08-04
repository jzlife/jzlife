<template>
	<view class="tall">
		<view class="orderTitle">
			<view class="orderTitleCh1" @click="showAll">
				全部
				<view class="orderLine" v-show="showAlls"></view>
			</view>
			<view class="orderTitleCh1" @click="showBuKuan">
				需补款
				<view class="orderLine" v-show="showBukuans"></view>
			</view>
			<view class="orderTitleCh1" @click="showDoing">
				未完成
				<view class="orderLine" v-show="showDoings"></view>
			</view>
			<view class="orderTitleCh1" @click="showDone">
				已完成
				<view class="orderLine" v-show="showDones"></view>
			</view>
		</view>
		<!-- 全部 -->
		<section class="dingdanAll" v-show="showAlls">
			<view class="dingdanCH1" v-for="(item,index) in dList" :key="index">
				<view class="dAddress_Time">
					<view class="dAddress">{{item.name}}</view>
					<view class="dingTime">{{item.msgs}}</view>
				</view>
				<view class="dTime">{{item.time}}</view>
				<view class="dPrice">￥{{item.price}}</view>
				<view class="dDanHao">配送订单:{{item.number}}</view>
				<view class="dingdanStatus" v-show="item.status == 1">
					<view class="chooseDefault">取消订单</view>
					<view class="dStatus">等待取件</view>
				</view>
				<view class="dingdanStatus" v-show="item.status == 2">
					<view class="chooseDefault">取消订单</view>
					<view class="dStatus">取件中</view>
				</view>
				<view class="dingdanStatusChuLi" v-show="item.status == 3">处理中</view>
				<view class="dingdanStatusChuLi" v-show="item.status == 4">送件中</view>
				<view class="endStatus">未完成</view>
			</view>
			<view class="zengGao" style="height: 100rpx;"></view>
		</section>
		<!-- 需补款 -->
		<section class="buKuan" v-show="showBukuans">
			<view class="buKuanDingDan" v-for="(item,index) in buKuanList" :key="index">
				<view class="buKuanTop">
					<view class="buKuanDanHao">配送订单:{{item.number}}</view>
					<view class="buKuanWenzi">需补款</view>
				</view>
				<view class="buKuanName_Msgs">
					<view class="buKuanName">{{item.name}}</view>
					<view class="buKuanMsgs">{{item.msgs}}</view>
					<view class="buKuanJiShi">{{item.jishi}}</view>
				</view>
				<view class="buKuanTime">{{item.time}}</view>
				<view class="buKuanPrice">
					<view class="buKuanPriced">已支付：￥{{item.priced}}</view>
					<view class="buKuanPricing">补款：￥{{item.pricing}}</view>
				</view>
				<view class="buKuanStatus">
					<view class="buKuanDefault" @click="defaultDingDan">取消订单</view>
					<view class="buKuanInto" @click="GotoBuKuan">补款</view>
				</view>
			</view>
			<view class="zengGao" style="height: 100rpx;"></view>
		</section>
		<!-- 未完成 -->
		<section class="dingdanAll" v-show="showDoings">
			<view class="dingdanCH1" v-for="(item,index) in wList" :key="index" @click="goTodetail(item.status)">
				<view class="dAddress_Time">
					<view class="dAddress">{{item.name}}</view>
					<view class="dingTime">{{item.msgs}}</view>
				</view>
				<view class="dTime">{{item.time}}</view>
				<view class="dPrice">￥{{item.price}}</view>
				<view class="dDanHao">配送订单:{{item.number}}</view>
				<view class="dingdanStatus" v-show="item.status == 1">
					<view class="chooseDefault">取消订单</view>
					<view class="dStatus">等待取件</view>
				</view>
				<view class="dingdanStatus" v-show="item.status == 2">
					<view class="chooseDefault">取消订单</view>
					<view class="dStatus">取件中</view>
				</view>
				<view class="dingdanStatusChuLi" v-show="item.status == 3">处理中</view>
				<view class="dingdanStatusZhiFu" v-show="item.status == 4">去支付</view>
				<view class="dingdanStatusChuLi" v-show="item.status == 5">等待送件</view>
				<view class="dingdanStatus" v-show="item.status == 6">
					<view class="chooseDefault">确认送达</view>
					<view class="dStatus">送件中</view>
				</view>
				<view class="endStatus">未完成</view>
			</view>
			<view class="zengGao" style="height: 100rpx;"></view>
		</section>
		<section class="Nav" v-show="showDones">
			<view class="DoneTopNumber_Status">
				<view class="DoneTopNumber">配送订单:xdjd1543548723</view>
				<view class="DoneTopStatus">已完成</view>
			</view>
			<view class="DoneTopAllMsgs">
				<view class="DoneTopName_Msgs">
					<view class="DoneTopName">翡翠城店(NO.1000)</view>
					<view class="DoneTopN_Msgs">衣物清洁等,共1次服务</view>
				</view>
				<view class="DoneTop_Time">2019-07-12 12:43</view>
				<view class="DoneTop_Price">￥10</view>
				<view class="DoneTopBtns">
					<view class="DoneBtns_Again" @click="ChooseAgain">再来一单</view>
					<view class="DoneBtns_Talk" @click="ChooseAgain">评价</view>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				dList: [{
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 1,
					status:1
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 2,
					status:2
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 3,
					status:3
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 4,
					status:1
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 5,
					status:4
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 6,
					status:1
				}],
				// 未完成
				wList: [{
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 1,
					status:1
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 2,
					status:2
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 3,
					status:3
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 4,
					status:6
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 5,
					status:4
				}, {
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等      共1次服务',
					time: '2019-07-11 12:43',
					price: 10,
					number: 'xjdj1364564549879',
					id: 6,
					status:5
				}],
				buKuanList: [{
					number: "xjsj113165456",
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等  共1次服务',
					jishi: '技师：共计需清理和修复30处问题',
					time: '2019-07-11 12:43',
					priced: 10,
					pricing: 999,
					id: 7,
					status:2
				}, {
					number: "xjsj113165456",
					name: '翡翠城店(NO.1000)',
					msgs: '衣物清洁等  共1次服务',
					jishi: '技师：共计需清理和修复30处问题',
					time: '2019-07-11 12:43',
					priced: 10,
					pricing: 999,
					id: 8,
					status:1
				}],
				showAlls: true, //全部订单显示
				showBukuans: false, //需补款
				showDoings: false, //显示未完成
				showDones: false, //显示已完成
			}
		},
		methods: {
			showAll() {
				this.showAlls = true
				this.showBukuans = false
				this.showDoings = false
				this.showDones = false
			},
			showBuKuan() {
				this.showAlls = false
				this.showBukuans = true
				this.showDoings = false
				this.showDones = false
			},
			showDoing() {
				this.showAlls = false
				this.showBukuans = false
				this.showDoings = true
				this.showDones = false
			},
			showDone() {
				this.showAlls = false
				this.showBukuans = false
				this.showDoings = false
				this.showDones = true
			},
			// 取消订单
			defaultDingDan() {
				uni.showModal({
					title:'取消订单',
					duration:2000,
					content:'订单由张三进行配送，费用为3元，将退还费用1元，优惠券4元，金额和优惠券将原路退回',
					showCancel:true,
					cancelText:'取消订单',
					confirmText:'补款',
					success:function (res) {
						if(res.confirm) {
							console.log("补款成功")
						}else if(res.cancel) {
							console.log("补款失败")
						}
					}
				})
			},
			// 补款
			GotoBuKuan() {
				uni.navigateTo({
					url:'../order/bukuan'
				})
			},
			// 未完成商品点击事件
			goTodetail(e) {
				if(e == 1) {
					uni.navigateTo({
						url:'../order/waitingGetGoods/waitingGetGoods'
					})
				}else if(e == 2) {
					uni.navigateTo({
						url:'../order/GetingGoods/GetingGoods'
					})
				}else if(e == 4) {
					uni.navigateTo({
						url:'../order/pay/pay'
					})
				}else if(e == 5) {
					uni.navigateTo({
						url:'../order/waitingShip/waitingShip'
					})
				}else if(e == 6) {
					uni.navigateTo({
						url:'../order/sendingGoods/sendingGoods'
					})
				}
			},
			ChooseAgain() {
				uni.navigateTo({
					url:'../order/finished/finishedDetail/finishedDetail'
				})
			}
		}
	}
</script>

<style>
	.tall {
		width: 100%;
		height: auto;
	}

	.orderTitle {
		z-index: 50;
		position: fixed;
		top: 80rpx;
		left: 0rpx;
		width: 100%;
		height: 104rpx;
		background-color: #F2F2F2;
		display: flex;
		justify-content: space-between;
	}

	.orderTitleCh1 {
		z-index: 40;
		position: relative;
		width: 25%;
		height: 106rpx;
		line-height: 106rpx;
		text-align: center;
		font-size: 36rpx;
		/* margin-top: 56px; */
		/* font-weight: bold; */
	}

	.orderLine {
		position: absolute;
		width: 50%;
		left: 25%;	
		height: 8rpx;
		background: #0A98D5;
		bottom: 14rpx;
	/* 	display: none;
		animation-fill-mode: forwards; */
	}

	/* section  订单1*/
	.dingdanAll {
		width: 100%;
		height: auto;
		overflow-y: scroll;
		margin-top: 112rpx;
	}

	.dingdanCH1 {
		position: relative;
		width: 100%;
		/* margin-left: 2%; */
		height: 300rpx;
		background: white;
		border-top: 1rpx solid #929292;
	}

	.dAddress_Time {
		position: absolute;
		top: 6rpx;
		left: 10rpx;
		width: 400rpx;
		height: 80rpx;
		/* border:1px solid black; */
	}

	.dAddress {
		height: 40rpx;
		width: 100%;
		line-height: 40rpx;
		font-size: 32rpx;
	}

	.dingTime {
		font-size: 26rpx;
		height: 40rpx;
		width: 100%;
		line-height: 40rpx;
	}

	.dTime {
		position: absolute;
		top: 4rpx;
		right: 14rpx;
		color: #929292;
		font-size: 24rpx;
	}

	.dPrice {
		position: absolute;
		top: 110rpx;
		left: 6rpx;
		font-size: 38rpx;
		width: 200rpx;
		height: 40rpx;
	}

	.dDanHao {
		position: absolute;
		color: #929292;
		font-size: 24rpx;
		width: 400rpx;
		left: 6rpx;
		bottom: 6rpx;
	}

	.dingdanStatus {
		position: absolute;
		top: 110rpx;
		right: 10rpx;
		width: 344rpx;
		height: 60rpx;
		/* border: 1px solid black; */
		display: flex;
		justify-content: space-between;

	}
	.dingdanStatusChuLi {
		position: absolute;
		top: 110rpx;
		right: 10rpx;
		width: 120rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: right;
		font-weight: bold;
		border-radius: 10rpx;
	}
	.dingdanStatusZhiFu {
		position: absolute;
		top: 110rpx;
		right: 10rpx;
		width: 120rpx;
		height: 60rpx;
		border: 1rpx solid #929292;
		text-align: center;
		line-height: 60rpx;
		color: red;
		border-radius: 10rpx;
	}

	.chooseDefault {
		width: 206rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		border-radius: 6rpx;
		background-color: #FF5053;
		color: white;
		font-size: 28rpx;
	}

	.dStatus {
		width: 120rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		border-radius: 20rpx;
		/* background-color: #FF5053; */
		color: black;
		font-size: 28rpx;
	}

	.endStatus {
		position: absolute;
		bottom: 6rpx;
		right: 0rpx;
		width: 120rpx;
		height: 50rpx;
		line-height: 60rpx;
		text-align: center;
		color: #929292;
	}

	/* 需要补款 */
	.buKuan {
		margin-top: 112rpx;
		width: 100%;
		height: auto;
		overflow-y: scroll;
	}

	.buKuanDingDan {
		position: relative;
		width: 100%;
		height: 344rpx;
		border-bottom: 1rpx solid #D8D8D8;
		background-color: white;
		margin-top: 10rpx;
	}

	.buKuanTop {
		display: flex;
		justify-content: space-between;
		width: 100%;
		height: 96rpx;
		border-bottom: 1rpx solid #D8D8D8;
	}

	.buKuanDanHao {
		margin-left: 2%;
		width: 320rpx;
		height: 96rpx;
		line-height: 96rpx;
		font-size: 24rpx;
		color: #C7C6CD;
	}

	.buKuanWenzi {
		margin-right: 2%;
		text-align: right;
		width: 120rpx;
		height: 96rpx;
		line-height: 96rpx;
		font-size: 24rpx;
		color: #C7C6CD;
	}

	.buKuanName_Msgs {
		position: absolute;
		top: 108rpx;
		left: 2%;
		width: 380rpx;
		height: 140rpx;
	}

	.buKuanName {
		height: 36rpx;
		width: 100%;
		line-height: 36rpx;
		font-size: 36rpx;
		font-weight: bold;
	}

	.buKuanMsgs {
		width: 100%;
		overflow: hidden;
		font-size: 28rpx;
		height: 28rpx;
		margin-top: 16rpx;
		line-height: 28rpx;
	}

	.buKuanJiShi {
		width: 100%;
		overflow: hidden;
		font-size: 26rpx;
		height: 28rpx;
		margin-top: 16rpx;
		line-height: 28rpx;
	}

	.buKuanTime {
		position: absolute;
		top: 54px;
		right: 2%;
		text-align: right;
		width: 224rpx;
		height: 30rpx;
		font-size: 24rpx;
		color: #C7C6CD;
	}

	.buKuanPrice {
		position: absolute;
		bottom: 6rpx;
		left: 2%;
		width: 390rpx;
		height: 36rpx;
		display: flex;
		justify-content: space-between;
	}

	.buKuanPriced,
	.buKuanPricing {
		width: 190rpx;
		height: 36rpx;
		line-height: 36rpx;
		font-size: 28rpx;
	}

	.buKuanStatus {
		position: absolute;
		bottom: 6rpx;
		right: 2%;
		width: 296rpx;
		height: 50rpx;
		display: flex;
		justify-content: space-between;
	}

	.buKuanDefault {
		width: 160rpx;
		height: 50rpx;
		line-height: 50rpx;
		text-align: center;
		border-radius: 6rpx;
		background-color: #FF5053;
		color: white;
		font-size: 28rpx;
	}

	.buKuanInto {
		width: 124rpx;
		height: 46rpx;
		border: 1rpx solid #F0F0F0;
		line-height: 50rpx;
		font-size: 28rpx;
		background-color: white;
		text-align: center;
	}
	/* 已完成 */
	.Nav {
		width: 100%;
		height: 240rpx;
		overflow: scroll;
		border-top: 1rpx solid #808080;
		margin-top: 114rpx;
	}
	.DoneTopNumber_Status {
		width: 96%;
		height: 60rpx;
		margin-left: 2%;
		display: flex;
		justify-content: space-between;
	}
	.DoneTopNumber {
		width: 300rpx;
		height: 60rpx;
		line-height: 60rpx;
		font-size: 24rpx;
		color: #C7C6CD;
	}
	.DoneTopStatus {
		width: 300rpx;
		height: 60rpx;
		line-height: 60rpx;
		font-size: 24rpx;
		color: #C7C6CD;
		text-align: right;
	}
	.DoneTopAllMsgs {
		position: relative;
		width: 96%;
		height: 180rpx;
		margin-left: 2%;
	}
	.DoneTopName_Msgs {
		position: absolute;
		top: 10rpx;
		left: 0rpx;
		width: 360rpx;
		height: 80rpx;
	}
	.DoneTopName {
		width: 100%;
		height: 50rpx;
		line-height: 50rpx;
		font-size: 32rpx;
		font-weight: bold;
	}
	.DoneTopN_Msgs {
		width: 100%;
		height: 30rpx;
		line-height: 30rpx;
		font-size: 24rpx;
		font-weight: bold;
	}
	.DoneTop_Time {
		position: absolute;
		top: 10rpx;
		right: 0rpx;
		height: 30rpx;
		width: 300rpx;
		color: #C7C6CD;
		text-align: right;
		font-size: 24rpx;
	}
	.DoneTop_Price {
		position: absolute;
		top: 108rpx;
		left: 0rpx;
		width: 100rpx;
		height: 60rpx;
		line-height: 60rpx;
		font-size: 32rpx;
		font-weight: bold;
	}
	.DoneTopBtns {
		position: absolute;
		top: 108rpx;
		right: 0rpx;
		width: 300rpx;
		height: 60rpx;
		/* border: 1rpx solid black; */
		display: flex;
		justify-content: space-between;
	}
	.DoneBtns_Again {
		width: 150rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		font-size: 32rpx;
		border: 1rpx solid #C7C6CD;
	}
	.DoneBtns_Talk {
		width: 120rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		font-size: 32rpx;
		border: 1rpx solid #C7C6CD;
	}
</style>
