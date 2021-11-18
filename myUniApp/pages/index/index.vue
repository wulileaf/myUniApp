<template>
	<view class="content" style="width: 100%;height: 100%;flex-wrap: wrap;">
		<block v-for="(item,index) in pageData" :key="index">
			<view class='sale-content' @tap="functModel(index)">
				<icon :class="'iconfont '+item.imgUrl" style="font-size: 40px;" class="gf"></icon>
				<text style="margin-top: 10%;font-size: 12px;color: #000;text-align: center;">{{item.name}}</text>
			</view>
		</block>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				pageData: this._profile.FunctData
			}
		},

		onLoad() {

		},

		methods: {
			functModel(e) {

			}
		}
	}
</script>

<style>
	@import url("/static/luicss/index.css");
	@import url("/static/proicon/proicon.css");
</style>
