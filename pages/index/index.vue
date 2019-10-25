<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<view class="text-area " :class="{red:isRed}" >
			<text class="title">{{title}}_{{name}}:{{age}}</text>
		</view>
		<view :class="[activeIndex==index?'menuActive':'menu']"  v-for="(item,index) in players" :key=item.name
		 @click="menuClick(index)">
			{{index}}_{{item.name}}_level:{{item.level}}
		</view>
		<scroll-view class="scv" scroll-x="true">
			<!-- 左右滚动 -->
			<view>0000</view>
			<view>1111</view>
			<view>2222</view>
			<view>3333</view>
			<view>4444</view>
			<view>5555</view>
			<view>6666</view>
			<view>7777</view>
			<view>8888</view>
			<view>9999</view>
		</scroll-view>
		<scroll-view class="scv" scroll-y="true">
			<!-- 左右滚动 -->
			<view>0000</view>
			<view>1111</view>
			<view>2222</view>
			<view>3333</view>
			<view>4444</view>
			<view>5555</view>
			<view>6666</view>
			<view>7777</view>
			<view>8888</view>
			<view>9999</view>
		</scroll-view>
	</view>
</template>

<script>
	let _self;
	export default {
		data() {
			return {
				title:'Index...',
				name:"Ghaya",
				age:25,
				players:[
					{"name":"Ghaya1","level":34},
					{"name":"Ghaya2","level":56},
					{"name":"Ghaya3","level":72}
				],
				isRed:true,
				activeIndex:0
			}
		},
		onLoad() {
			_self = this;
			setTimeout(()=>{
				_self.age = 26;
			},3000)
			console.log('onload');
		},
		onShow() {
			console.log('onshow');
		},
		onHide() {
			console.log('onhide');
		},
		methods:{
			menuClick:(index)=>{
				_self.activeIndex = index;
			}
		}
	}
</script>
width
<style>
	scroll-view{display: flex;}
	.scv{width:90%;margin:0 auto;background:#00BFFF;flex-wrap: nowrap;white-space: nowrap;}
	.scv view{width:50%;height:90px;background:#FFA200;display: inline-block;}
	.red{color:red;}
	.menu{padding:10px;float:left;margin:5px;line-height:36x;}
	.menuActive{padding:10px;float:left;margin:5px;line-height:36x;color:#FFA200 !important;}
	.content {display:flex;flex-direction:column;align-items:center;justify-content:center;}
	.logo {height:200rpx;width:200rpx;margin-top:200rpx;margin-left:auto;margin-right:auto;margin-bottom:50rpx;}
	.text-area {display:flex;justify-content:center;}
	.title {font-size:36rpx;color:#8f8f94;}
</style>
