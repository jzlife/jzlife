<template>
	<view class="content">
		<view class="logo">
			<open-data type="userAvatarUrl"></open-data>
		</view>
		<view class="text-area">
			<view class="CH1 weixin" @click="phoneRegis">微信一键登录</view>
			<button class="CH1 phone" @getphonenumber="getPhoneNumber" open-type="getPhoneNumber">手机号登录</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		onLoad() {
			// uni.getSetting({
			// 	success: (res) => {
			// 		// console.log(res.authSetting['scope.userLocation'])
			// 		if(res.authSetting['scope.userLocation']) {
			// 			uni.getUserInfo({
			// 				success: (res) => {
			// 					console.log(res)
			// 				}
			// 			})
			// 		}
			// 		// this.UserImgs = res.avatarUrl
			// 	}
			// })
		},
		methods: {
			phoneRegis() {
				uni.switchTab({
					url: '../index/index'
				})
				// uni.authorize({
				// 	scope: 'scope.userLocation',
				// 	success() {
				// 		console.log("123")
				// 		uni.userLocation({
				// 			success: (res) => {
				// 				console.log(res )
				// 			}
				// 		})
				// 	},
				// 	fail() {
				// 		console.log("456")
				// 	}
				// })
			},
			getPhoneNumber(e) {
				var that = this
				var status = e.target.errMsg
				console.log(e)
				console.log(status)
				uni.login({
					success(res) {
						if (status == 'getPhoneNumber:ok') {
							uni.switchTab({
								url:'../index/index'
							})
							// uni.request({
							// 	url: '',
							// 	data: {
							// 		encryptedData: e.detail.encryptedData,
							// 		iv: e.detail.iv,
							// 		code: res.code
							// 	},
							// 	methods: "GET",
							// 	header: {
							// 		'content-type': 'application/json'
							// 	},
							// 	success(res) {
							// 		console.log(res)
							// 		if (res.data.Code == 200) {
							// 			uni.showToast({
							// 				title: '授权成功'
							// 			})
							// 			uni.switchTab({
							// 				url: '../index/index'
							// 			})
							// 		} else {
							// 			uni.showToast({
							// 				title: res.data.Message,
							// 				icon: 'none'
							// 			})
							// 		}
							// 	},
							// 	fail(err) {
							// 		uni.showToast({
							// 			title: res.data.Message,
							// 			icon: 'none'
							// 		})
							// 	}
							// })
						} else if (status == 'getPhoneNumber:fail user deny') { //拒绝授权 
							uni.showToast({
								title: '您拒绝了授权',
								icon: 'none',
								duration: 2000
							})
							uni.navigateTo({
								url: '/pages/login/login'
							})
						} else if (status == 'getPhoneNumber:fail 用户未绑定手机，请先在微信客户端进行绑定后重试') {
							uni.showToast({
								title: '您的微信未绑定手机号',
								icon: 'none',
								duration: 3000
							})

							wx.navigateTo({
								url: '/pages/login/login',
							})
						}else {
							uni.showToast({
								title:'网络繁忙，请稍后再试',
								icon:'none',
								duration:2000
							})
						}
					},
					fail(err) {
						wx.showToast({
							title:'获取登录态失败，请检查网络',
							icon:'none',
							duration:2000
						})
					}
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		border-radius: 50%;
		margin-top: 200upx;
		overflow: hidden;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50upx;
	}

	.text-area {
		position: relative;
		display: flex;
		justify-content: center;
		margin-top: 100upx;
		width: 475upx;
		height: 200upx;
	}

	.CH1 {
		position: absolute;
		width: 100%;
		height: 80rpx;
		border-radius: 10rpx;
		text-align: center;
		line-height: 80rpx;
		font-size: 30rpx;
	}

	.weixin {
		top: 0rpx;
		background-color: green;
		color: white;
	}

	.phone {
		bottom: 0rpx;
		background-color: white;
		color: #000000;
		border: 1rpx solid #C0C0C0;
	}
</style>
