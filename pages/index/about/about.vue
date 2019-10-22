<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello...23'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.red{
		color: #FF0000;
	}
</style>
