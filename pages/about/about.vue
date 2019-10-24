<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view>
			<picker :value="index" :range="years" @change="dateChange()" >
				<view>{{years[index]}}</view>
			</picker>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				index:0,
				yearText:"请选择年份",
				years:[1993,1994,1995,1996,1997],
				title: 'About...'
			}
		},
		onLoad() {

		},
		methods:{
			dateChange:(e)=>{
				console.log(e);
				let index = e.target.value;
				this.yearText = this.years[index];
			}
		}
	}
</script>

<style>
	.red{
		color: #FF0000;
	}
</style>
