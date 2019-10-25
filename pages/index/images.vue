<template>
    <view>
		<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
			<swiper-item v-for="(item,index) in arrStr" :key="item">
			    <view :class="'imgtab uni-bg-'+arrColor[index]">{{arrStr[index]}}</view>
			</swiper-item>  
		</swiper>
    </view>
</template>

<script>
	export default {
	    data() {
	        return {
				arrStr:['A','B','C','D'],
				arrColor:['red','blue','orange','green'],
	            background: ['color1', 'color2', 'color3'],
	            indicatorDots: true,
	            autoplay: true,
	            interval: 2500,
	            duration: 1000
	        }
	    },
	    methods: {
			
	    }
	}
</script>
	
<style>
	swiper-item{
			background:#FFAA00;height: 2px;width: 100%;
	}
	.imgtab{
		height: 175px;
		padding: 5px 5px 10px 20px;
	}
</style>
