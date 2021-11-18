<template>
	<view class="content">
		<button type="primary" @click="checkIsSupportSoterAuthentication">检查支持的认证方式</button>
		<button type="primary" @click="checkIsSoterEnrolledInDeviceFingerPrint">检查是否录入指纹</button>
		<button type="primary" @click="checkIsSoterEnrolledInDeviceFaceID">检查是否录入FaceID</button>
		<button type="primary" @click="startSoterAuthenticationFingerPrint">开始指纹认证</button>
		<button type="primary" @click="startSoterAuthenticationFaceID">开始FaceID认证</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		onLoad() {

		},
		methods: {
			// 检查支持的认证方式
			checkIsSupportSoterAuthentication() {
				uni.checkIsSupportSoterAuthentication({
					success(res) {
						// console.log(res);
						console.log("11-----success---------" + JSON.stringify(res));
					},
					fail(err) {
						// console.log(err);
						console.log("12-----fail---------" + JSON.stringify(err));
					},
					complete(res) {
						// console.log(res);
						console.log("13-----complete---------" + JSON.stringify(res));
					}
				})
			},

			// 检查是否录入指纹
			checkIsSoterEnrolledInDeviceFingerPrint() {
				uni.checkIsSoterEnrolledInDevice({
					checkAuthMode: 'fingerPrint',
					success(res) {
						console.log("21-----success---------" + JSON.stringify(res));
					},
					fail(err) {
						// console.log(err);
						console.log("22-----fail---------" + JSON.stringify(err));
					},
					complete(res) {
						console.log("23-----complete---------" + JSON.stringify(res));
					}
				})
			},

			// 检查是否录入
			checkIsSoterEnrolledInDeviceFaceID() {
				uni.checkIsSoterEnrolledInDevice({
					checkAuthMode: 'facial',
					success(res) {
						console.log("31-----success---------" + JSON.stringify(res));
					},
					fail(err) {
						// console.log(err);
						console.log("32-----fail---------" + JSON.stringify(err));
					},
					complete(res) {
						// console.log(res);
						console.log("33-----complete---------" + JSON.stringify(res));
					}
				})
			},

			// 开始指纹认证
			startSoterAuthenticationFingerPrint() {
				uni.startSoterAuthentication({
					requestAuthModes: ['fingerPrint'],
					challenge: '123456',
					authContent: '请用指纹解锁',
					success(res) {
						// console.log(res);
						console.log("41-----success---------" + JSON.stringify(res));
					},
					fail(err) {
						// console.log(err);
						console.log("42-----fail---------" + JSON.stringify(err));
					},
					complete(res) {
						// console.log(res);
						console.log("43-----complete---------" + JSON.stringify(res));
					}
				})
			},

			// 开始FaceID认证
			startSoterAuthenticationFaceID() {
				uni.startSoterAuthentication({
					requestAuthModes: ['facial'],
					challenge: '123456',
					authContent: '请用FaceID解锁',
					success(res) {
						console.log(res);
						console.log("51-----success---------" + JSON.stringify(res));
					},
					fail(err) {
						// console.log(err);
						console.log("52-----fail---------" + JSON.stringify(err));
					},
					complete(res) {
						console.log(res);
						console.log("53-----complete---------" + JSON.stringify(res));
					}
				})
			}
		}
	}
</script>

<style>
	button {
		width: 200px;
		margin: 20px auto;
	}
</style>
