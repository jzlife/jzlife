<template>
	<view class="tall">
		<view class="Tops">
			<view class="TopName_Msgs">
				<view class="TopName">已完成</view>
				<view class="TopMsgs">感谢您得光临</view>
			</view>
			<view class="Top_Choose">
				<view class="TopChoose_Again" @click="chooseAgain">再来一单</view>
				<view class="TopChoose_evaluation" @click="chooseEvaluation">去评价</view>
			</view>
		</view>
		<view class="Body_FuWu">
			<view class="Body_FuWu_Ch1">服务门店</view>
			<view class="Body_FuWu_Ch1">翡翠城店(NO.10000)</view>
			<view class="Body_FuWu_Ch1">具体地址:国际人才市场</view>
		</view>
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
		<view class="Bottom_Msg">
			<view class="Bottom_Address">
				<view class="Bottom_Address_Name">取件地址</view>
				<view class="Bottom_Address_Detail">
					<view class="Bottom_Addr">新希望国际A座1002</view>
					<view class="Bottom_Addr_UserMsgs">xxx先生   4647876464</view>
				</view>
			</view>
			<view class="Bottom_MsgsCh1">
				<view class="BottomMsgsLeft">完成时间</view>
				<view class="BottomMsgsRight">2019-07-12 12:23</view>
			</view>
			<view class="Bottom_MsgsCh1">
				<view class="BottomMsgsLeft">管家信息</view>
				<view class="BottomMsgsRight">管家xxx   13245678912</view>
			</view>
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
			// 再来一单
			chooseAgain() {
				uni.showModal({
					title:'再来一单',
					content:'你确定要再来一单吗？',
					cancelText:'取消',
					success(res) {
						if(res.confirm){
							console.log('11')
						}else if(res.cancel){
							console.log('22')
						}
					}
				})
			},
			// 去评价
			chooseEvaluation() {
				uni.showModal({
					title:'去评价',
					content:'你确定要评价吗？',
					cancelText:'取消',
					success(res) {
						if(res.confirm){
							uni.navigateTo({
								url:'../../../order/finished/finishedDetail/evaluation/evaluation'
							})
						}else if(res.cancel){
							console.log('22')
						}
					}
				})
			}
		}
	}
</script>

<style>
	.tall {
		width: 100%;
		height: 100%;
	}
	.Tops {
		position: relative;
		width: 100%;
		height: 340rpx;
		border-bottom: 1rpx solid #6D6D72;
	}
	.TopName_Msgs {
		position: absolute;
		width: 50%;
		height: 80rpx;
		/* border: 1rpx solid black; */
		left: 25%;
		top: 64rpx;
	}
	.TopName {
		width: 100%;
		height: 48rpx;
		line-height: 48rpx;
		font-size: 34rpx;
		text-align: center;
		font-weight: bold;
	}
	.TopMsgs {
		width: 100%;
		height: 32rpx;
		line-height: 32rpx;
		font-size: 26rpx;
		text-align: center;
		font-weight: bold;
		margin-bottom: 0rpx;
	}
	.Top_Choose {
		position: absolute;
		bottom: 80rpx;
		width: 56%;
		height: 60rpx;
		left: 22%;
		display: flex;
		justify-content: space-between;
		
	}
	.TopChoose_Again {
		width: 134rpx;
		height: 60rpx;
		border: 1rpx solid #C7C6CD;
		color: black;
		font-size: 26rpx;
		text-align: center;
		line-height: 60rpx;
	}
	.TopChoose_evaluation {
		width: 134rpx;
		height: 60rpx;
		font-size: 26rpx;
		border: 1rpx solid #C7C6CD;
		color: #007AFF;
		text-align: center;
		line-height: 60rpx;
	}
	.Body_FuWu {
		width: 100%;
		height: 150rpx;
		margin-top: 10rpx;
		border-top: 1rpx solid #6D6D72;
		border-bottom: 1rpx solid #6D6D72;
	}
	.Body_FuWu_Ch1 {
		height: 40rpx;
		width: 96%;
		margin-left: 2%;
		/* border: 1rpx solid black; */
		font-size: 24rpx;
		line-height: 40rpx;
		margin-top: 10rpx;
	}
	/* 中下部展示 */
	.Body_Bottom {
		width: 100%;
		height: 372rpx;
		border-top: 1rpx solid #6D6D72;
		border-bottom: 1rpx solid #6D6D72;
		margin-top: 10rpx;
	}
	.Body_Bottom_Danhao_Time {
		width: 100%;
		height: 80rpx;
		border-bottom: 1rpx solid #6D6D72;
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
		border-bottom: 1rpx solid #6D6D72;
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
	/* 下部信息 */
	.Bottom_Msg {
		width: 100%;
		height: 212rpx;
		border-top: 1rpx solid #6D6D72;
		margin-top: 10rpx;
	}
	.Bottom_Address{
		position: relative;
		width: 100%;
		height: 90rpx;
		border-bottom: 1rpx solid #6D6D72;
		/* border: 1rpx solid red; */
	}
	.Bottom_Address_Name {
		position: absolute;
		width: 120rpx;
		height: 60rpx;
		line-height: 60rpx;
		left: 2%;
		top: 0rpx;
		font-size: 24rpx;
		
	}
	.Bottom_Address_Detail {
		position: absolute;
		top: 0rpx;
		right: 2%;
		text-align: right;
		height: 80rpx;
		/* border: 1rpx solid black; */
		width: 300rpx;
	}
	.Bottom_Addr,.Bottom_Addr_UserMsgs {
		text-align: right;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 24rpx;
		/* border: 1rpx solid black; */
		width: 100%;
	}
	.Bottom_MsgsCh1 {
		position: relative;
		width: 100%;
		height: 60rpx;
		border-bottom: 1rpx solid #6D6D72;
		/* border: 1rpx solid black; */
		
	}
	.BottomMsgsLeft {
		position: absolute;
		top:0rpx;
		height: 60rpx;
		width: 100rpx;
		left: 2%;
		line-height: 60rpx;
		font-size: 24rpx;
	}
	.BottomMsgsRight {
		position: absolute;
		top:0rpx;
		height: 60rpx;
		width: 300rpx;
		right: 2%;
		text-align: right;
		line-height: 60rpx;
		font-size: 24rpx;
	}
</style>
