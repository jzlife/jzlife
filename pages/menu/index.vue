<template>
	<view class="tall">
		<view class="menu">
			<view class="banner">
				<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
					<swiper-item v-for="(item, index) in adList" :key="index">
						<a :href="item.url">
							<image :src="item.picture" mode="scaleToFill"></image>
						</a>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<view class="address">
			<view class="addressWhere">
				<image src="../../static/images/lat.png" mode=""></image>
				<view class="addressName">
					新希望国际A座
				</view>
			</view>
			<image class="nowFounds" src="../../static/images/jiantou.png" mode=""></image>
		</view>
		<!-- 内容展示部分 -->
		<view class="msgsShow">
			<view class="msgsLeft">
				<view class="msgsLCh1" v-for="(item,index) in goodsList" :key="index" :class="{category_active:categroy_id == item.id}"
				 @click="chooseClass(item.id,item.tag)">{{item.name}}</view>
			</view>
			<scroll-view scroll-y="true" scroll-into-view="tag" scroll-with-animation="true" class="msgsRight">
				<view class="msgsRCh1" v-for="(item,index) in goodsList" :key="index" :id="item.tag">
					<view class="msgsRCh1NAddress">
						<view class="msgsRCh1Name">{{item.name}}</view>
						<view class="msgsLine"></view>
					</view>
					<view class="msgsRCh1Goods" v-for="(items,ind) in item.Date" :key="ind">
						<view class="msgsR_Imgs">
							<image :src="items.imgs" mode=""></image>
						</view>
						<view class="msgsR_Introductions">
							<view class="msgsDetail">{{items.msgs}}</view>
							<view class="goodsPrice">￥{{items.price}}</view>
							<image src="../../static/images/add.png" mode="" @click="AddGoods"></image>
						</view>
					</view>
				</view>
				<view class="zengGao" style="height: 100rpx;">
				</view>
			</scroll-view>
		</view>
		<!-- 选择规格组件 -->
		<view class="mengban" v-show="chooseGuiGe"></view>
		<view class="Specifications" v-show="chooseGuiGe">
			<section class="SpectionImgs">
				<image src="../../static/images/2.jpg" mode=""></image>
				<view class="SpectionImgsLMsgs">
					<text class="SpecitionsMsgsTitle">T恤,抹胸</text>
					<text class="SpectionsMsgsMore">T恤,抹胸之类得轻便衣服</text>
				</view>
			</section>
			<section class="SpecMsgsMore">
				<view class="SpecMsgsMoreCh1">
					<view class="MsgsChNames">
						专业养护
					</view>
					<image src="../../static/images/true.png" mode=""></image>
				</view>
				<view class="SpecMsgsMoreCh1">
					<view class="MsgsChNames">
						专业修复
					</view>
					<image src="../../static/images/true.png" mode=""></image>
				</view>
				<view class="SpecMsgsMoreCh2">
					<view class="SpecMsgsMoreCh2Title">
						<view class="MsgsChNames">
							特殊污渍
						</view>
						<image src="../../static/images/true.png" mode=""></image>
					</view>
					<view class="ShowSpecion_Detial">
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
						<view class="Detial_Ch1">油污</view>
					</view>
				</view>
				<!-- 详情部分 -->
				<view class="Detial_MsgsMore">
					<view class="Detial_MsgsMore_Title">
						服务描述
					</view>
					<view class="Detial_MsgsMoreAbout">
						&nbsp;&nbsp;此项目服务于经济技术都就是倒计时定价技术等级是的就是地方技即使对方
						<br>
						专业养护，啊哈哈哈
						<br>
						专业养护，啊哈哈哈
						<br>
						专业养护，啊哈哈哈
						<br>
						专业养护，啊哈哈哈
					</view>
				</view>
				<view class="Detial_MsgsMoreCh2">
					<view class="Detial_MsgsMore_Title">
						品牌理念
					</view>
					<view class="Detial_MsgsMoreAbout">
						&nbsp;&nbsp;此项目服务于经济技术都就是倒计时定价技术等级是的就是地方技即使对方
						<br>
						专业养护，啊哈哈哈
					</view>
				</view>
			</section>
			<section class="chooseCartOnes">
				<view class="chooseGoodsTalk">
					<view class="chooseGoodsPrice">￥45</view>
					<view class="choooseGoodsMsgs">
						还是不错得哈哈哈哈哈黑恶黑
					</view>
				</view>
				<view class="chooseHowMuch">
					<image src="../../static/images/subN.png" mode="" @click="subNum()"></image>
					<text class="chooseNumber">{{count}}</text>
					<image src="../../static/images/addN.png" mode="" @click="addNum()"></image>
				</view>
				<view class="chooseWhere">
					<view class="chooseHuiYuan">
						会员￥19.5
					</view>
					<view class="chooseCart" @click="ComingCart">
						加入购物车
					</view>
				</view>
			</section>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 4000,
				duration: 3500,
				adList: [{
						url: "",
						picture: "../../static/images/1.jpg",

						index: 1
					},
					{
						url: "",
						picture: "../../static/images/2.jpg",
						index: 2
					},
					{
						url: "",
						picture: "../../static/images/3.jpg",
						index: 3
					},
				],
				categroy_id: 1, //对应得种类下标
				goodsList: [
					{
						Date: [{
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 13.5
						}, {
							imgs: '../../static/images/2.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 116.5
						}],
						name: "衣物清洁",
						id: 1,
						tag:'clothes'
					},
					{
						Date: [{
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 33.5
						}, {
							imgs: '../../static/images/2.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 7.9
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 6.5
						}, {
							imgs: '../../static/images/3.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 13.5
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 33.5
						}, {
							imgs: '../../static/images/2.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 7.9
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 6.5
						}],
						name: "裤子清洁",
						id: 2,
						tag:'trousers'
					},
					{
						Date: [{
							imgs: '../../static/images/3.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 13.5
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 33.5
						}, {
							imgs: '../../static/images/2.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 7.9
						}],
						name: "窗帘清洁",
						id: 3,
						tag:'curtain'
					},
					{
						Date: [{
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 6.5
						}, {
							imgs: '../../static/images/3.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 13.5
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 33.5
						}, {
							imgs: '../../static/images/2.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 7.9
						}],
						name: "鞋子清洁",
						id: 4,
						tag:'shoes'
					}, {
						Date: [{
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 6.5
						}, {
							imgs: '../../static/images/3.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 13.5
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 9.5
						}, {
							imgs: '../../static/images/2.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 13.5
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 14.3
						}, {
							imgs: '../../static/images/3.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 19.7
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 19.7
						}],
						name: "皮具清洁",
						id: 5,
						tag:'leather'
					}, {
						Date: [{
							imgs: '../../static/images/2.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 19.0
						}, {
							imgs: '../../static/images/3.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 18.0
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 13.2
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 15.7
						}],
						name: '帽子清洁',
						id: 6,
						tag:'hat'
					}, {
						Date: [{
							imgs: '../../static/images/2.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 39.2
						}, {
							imgs: '../../static/images/3.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 1.7
						}, {
							imgs: '../../static/images/1.jpg',
							msgs: 'T恤,背心,应有竟有得用户洗衣,T恤,背心,应有竟有得用户洗衣T恤,背心,应有竟有得用户洗衣',
							price: 11.2
						}],
						name: '其它清洁',
						id: 7,
						tag:'other'
					}
				],
				chooseGuiGe: false, //显示组件
				count: 1, //选择数量
				name:'',
				tag:'clothes',
			}
		},
		methods: {
			chooseClass(id,index) {
				this.categroy_id = id
				this.tag = index
			},
			// scroll(e) {
			// 	this.scrollTop = parseInt(e.detail.scrollTop)
			// 	
			// },
			subNum() {
				this.count--
				if (this.count <= 0) {
					this.count = 0
				}
			},
			addNum() {
				this.count++
			},
			AddGoods() {
				this.chooseGuiGe = true
			},
			ComingCart() {
				this.chooseGuiGe = false
			}
		},
		mounted() {
			// this.showChooseGoods()
		}
	}
</script>

<style>
	.tall {
		position: relative;
		width: 100%;
		height: 100%;
	}

	.menu {
		width: 100%;
		height: 360rpx;
		background-color: #007AFF;
	}

	.banner {
		height: 360rpx;
		background: #BBBBBB;
	}

	a {
		display: inline-block;
		width: 100%;
		height: 360rpx;
	}

	.swiper {
		height: 360rpx;
	}

	image {
		width: 100%;
		height: 100%;
	}

	/* address */
	.address {
		position: relative;
		width: 100%;
		height: 80rpx;
		background-color: #FFFFFF;
	}

	.addressWhere {
		position: relative;
		width: 400rpx;
		height: 80rpx;
		margin-left: 20rpx;
	}

	.addressWhere image {
		position: absolute;
		top: 20rpx;
		width: 40rpx;
		height: 40rpx;
		left: 2rpx;
	}

	.addressName {
		position: absolute;
		top: 0rpx;
		height: 80rpx;
		line-height: 96rpx;
		width: auto;
		left: 59rpx;
	}

	.nowFounds {
		position: absolute;
		top: 20rpx;
		right: 20rpx;
		width: 40rpx;
		height: 40rpx;
	}

	/* 信息展示部分 */
	.msgsShow {
		width: 100%;
		height: 826rpx;
		display: flex;
		justify-content: space-between;
		overflow: hidden;
		/* background-color: rgba(1,1,1,.5); */
	}

	.msgsLeft {
		width: 30%;
		height: 100%;
		background-color: #C8C8C8;
	}

	.msgsLCh1 {
		width: 100%;
		height: 80rpx;
		border-bottom: 1rpx solid #929292;
		font-size: 32rpx;
		font-weight: 600;
		text-align: center;
		line-height: 80rpx;
	}

	.category_active {
		background-color: #fff;
	}

	.msgsRight {
		overflow-y: scroll;
		width: 70%;
		height: 100%;
	}

	.msgsRCh1 {
		position: relative;
		width: 94%;
		height: auto;
		/* height: 83px; */
		margin-left: 3%;
		margin-top: 10rpx;
		/* border: 1rpx solid #B2B2B2; */
	}
	
	.msgsRCh1NAddress {
		position: relative;
		width: 100%;
		border-top: 2rpx solid #B2B2B2;
		height: 60rpx;
	}
	
	.msgsRCh1Name {
		font-size: 36rpx;
		height: 30px;
		line-height: 60rpx;
		width: 30%;
		text-align: center;
	}
	
	.msgsLine{
		position: absolute;
		right: -16rpx;
		width: 68%;
		border-top: 1rpx solid #B2B2B2;
		top: 29rpx;
	}
	
	.msgsRCh1Goods {
		position: relative;
		width: 100%;
		height: 180rpx;
		margin-top: 12rpx;
		border: 1rpx solid #B2B2B2;
	}
	
	.msgsR_Imgs {
		position: absolute;
		width: 28%;
		height: 90%;
		overflow: hidden;
		top: 5%;
		left: 2%;
	}

	.msgsR_Imgs image {
		width: 100%;
		height: 100%;
	}

	.msgsR_Introductions {
		position: absolute;
		width: 67%;
		height: 140rpx;
		right: 0;
		top: 14rpx;
	}

	.msgsR_Introductions .msgsDetail {
		/* word-wrap: break-word; */
		/* word-break: normal; */
		width: 100%;
		height: 96rpx;
		overflow-y: hidden;
		/* border: 1rpx solid black; */

	}

	.goodsPrice {
		position: absolute;
		bottom: -14rpx;
		width: 400rpx;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 28rpx;
		color: red;
		font-weight: bold;
	}

	.msgsR_Introductions image {
		position: absolute;
		right: 12rpx;
		bottom: -14rpx;
		height: 50rpx;
		width: 50rpx;
	}

	.mengban {
		position: fixed;
		top: 0rpx;
		left: 0rpx;
		z-index: 20;
		width: 100%;
		height: 100%;
		background-color: rgba(1, 1, 1, .4);
	}

	/* 组件部分 */
	.Specifications {
		z-index: 25;
		position: absolute;
		width: 90%;
		height: 86%;
		background-color: white;
		border-radius: 20rpx;
		top: 7%;
		left: 5%;
		overflow: hidden;

	}

	.SpectionImgs {
		position: relative;
		width: 100%;
		height: 302rpx;
		border: 1rpx solid #6D6D72;
	}

	.SpectionImgs image {
		position: absolute;
		top: 0rpx;
		left: 0rpx;
		width: 100%;
		height: 100%;
	}

	.SpectionImgsLMsgs {
		position: absolute;
		bottom: 10rpx;
		left: 10rpx;
		width: 80%;
		height: 10rpx;
		/* border: 1px solid black; */
	}

	.SpecitionsMsgsTitle {
		font-size: 32rpx;
		font-weight: 600;
		height: 60rpx;
		width: 100%;
		line-height: 60rpx;
	}

	.SpectionsMsgsMore {
		position: absolute;
		left: 0rpx;
		bottom: 4rpx;
		font-size: 24rpx;
		height: 40rpx;
		line-height: 40rpx;
		width: 100%;
		overflow: hidden;
	}

	.SpecMsgsMore {
		width: 100%;
		height: 600rpx;
		overflow-y: scroll;
	}

	.SpecMsgsMoreCh1 {
		position: relative;
		font-size: 28rpx;
		height: 81rpx;
		margin-top: 20rpx;
		border: 1rpx solid #6D6D72;
		width: 94%;
		margin-left: 3%;
	}

	.MsgsChNames {
		position: absolute;
		left: 10rpx;
		height: 81rpx;
		width: 200rpx;
		line-height: 82rpx;
		font-size: 32rpx;
	}

	.SpecMsgsMoreCh1 image {
		position: absolute;
		right: 10rpx;
		height: 40rpx;
		width: 40rpx;
		top: 21rpx;
	}

	.SpecMsgsMoreCh2 {
		position: relative;
		width: 94%;
		height: 360rpx;
		margin-top: 20rpx;
		margin-left: 3%;
		border: 1rpx solid #6D6D72;
		font-size: 28rpx;
	}

	.SpecMsgsMoreCh2Title {
		width: 100%;
		height: 82rpx;
	}

	.SpecMsgsMoreCh2 image {
		position: absolute;
		top: 26rpx;
		right: 10rpx;
		height: 40rpx;
		width: 40rpx;
	}

	.ShowSpecion_Detial {
		width: 100%;
		height: 282rpx;
		position: absolute;
		bottom: 8rpx;
	}

	.Detial_Ch1 {
		width: 128rpx;
		height: 56rpx;
		text-align: center;
		line-height: 56rpx;
		border: 1rpx solid #999;
		font-size: 24rpx;
		margin-left: 36rpx;
		margin-top: 24rpx;
		float: left;
	}

	/* 详情展示部分 */
	.Detial_MsgsMore {
		border: 1rpx solid black;
		width: 100%;
		height: 360rpx;
		margin-top: 20rpx;
	}

	.Detial_MsgsMore_Title,
	.Detial_MsgsMore_Title {
		width: 94%;
		margin-left: 3%;
		height: 86rpx;
		line-height: 86rpx;
		font-size: 36rpx;
	}

	.Detial_MsgsMoreAbout,
	.Detial_MsgsMoreAbout {
		width: 94%;
		margin-left: 3%;
		height: 260rpx;
		overflow-y: scroll;
		font-size: 30rpx;
		margin-top: 0rpx;
	}

	.Detial_MsgsMoreCh2 {
		/* border-bottom:1px solid black; */
		height: 300rpx;
		width: 100%;
	}


	/* 按钮选择 */
	.chooseCartOnes {
		position: absolute;
		bottom: 0rpx;
		width: 100%;
		height: 176rpx;
		border-top: 1rpx solid #6D6D72;
	}

	.chooseGoodsTalk {
		width: 66%;
		height: 80rpx;
		margin-top: 10rpx;
		margin-left: 10rpx;
	}

	.chooseGoodsPrice {
		width: 120rpx;
		height: 36rpx;
		line-height: 36rpx;
		font-size: 36rpx;
		font-weight: 600;
	}

	.chooseGoodsMsgs {
		font-size: 24rpx;
		font-size: 20rpx;
		width: 100%;
		overflow: hidden;
	}

	.chooseHowMuch {
		position: absolute;
		right: 20rpx;
		top: 20rpx;
		width: 160rpx;
		height: 60rpx;
		margin-right: 10rpx;
		display: flex;
		justify-content: space-between;
	}

	.chooseHowMuch image {
		width: 60rpx;
		height: 60rpx;

	}

	.chooseNumber {
		width: 36rpx;
		height: 60rpx;
		text-align: center;
		line-height: 60rpx;
		font-size: 36rpx;
	}

	.chooseWhere {
		position: absolute;
		bottom: 10rpx;
		width: 90%;
		height: 60rpx;
		margin-left: 5%;
		display: flex;
		justify-content: space-between;

	}

	.chooseHuiYuan,
	.chooseCart {
		width: 40%;
		height: 60rpx;
		border: 1rpx solid #333333;
		line-height: 60rpx;
		color: red;
		text-align: center;
		border-radius: 10rpx;
	}

	.chooseCart {
		color: black;
	}
</style>
