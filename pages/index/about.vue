<template>
	<view class="content">
		<page-head :title="title"></page-head>
		<view class="uni-title uni-common-pl">普通选择器(年份选择)</view>
		<view class="uni-list">
			<view class="uni-list-cell">
				<view class="uni-list-cell-left">
					当前选择
				</view>
				<view class="uni-list-cell-db">
					<picker @change="dateChange" :value="years[index]" :range="years"><!-- range-key="name" 在数组有属性名的情况下 -->
						<view class="uni-input">{{isYearText?yearText:years[index]}}</view> 
					</picker>
				</view>
			</view>
		</view>
		<!-- <view>
			<text>aaaaaaa</text>
			<picker-view v-if="visible" :indicator-style="indicatorStyle" :value="value" @change="bindChange">
				<picker-view-column>
					<view class="item" v-for="(item,index) in players" :key="index">{{item}}</view>
				</picker-view-column>
				<picker-view-column>
					<view class="item" v-for="(item,index) in equips" :key="index">{{item}}</view>
				</picker-view-column>
				<picker-view-column>
					<view class="item" v-for="(item,index) in locals" :key="index">{{item}}</view>
				</picker-view-column>
			</picker-view>
		</view> -->
	</view>
</template>

<script>
	export default {
		data() {
			let arr1 = [
				{
					"R1":[
						{"1":['1','2','3','4','5']},
						{"2":['1','2','3']},
						{"3":['1','2','3','4','5','6']}
					],
				},
				{
					"R2":[
						{"1":['1','2','3','4']},
						{"2":['1','2','3']},
						{"3":['1','2','3','4','5','6']},
						{"4":['1','2','3','4']},
						{"5":['1','2','3','4','5']}
					]
				}
			]
			return {
				index:0,
				yearText:"请选择年份",
				isYearText:true,
				visible:true,
				years:['1993','1994','1995','1996','1997'],
				months:['01','02','03','04','05','06',],
				players:['Ghaya','Komomo','Asuna','Kosame','Nagisa'],
				equips:['yozura','star','Terraria'],
				locals:['nihon','compare','卧槽'],
				title: 'About...',
				arr1:arr1
			}
		},
		onLoad() {

		},
		methods:{
			dateChange:function(e){
				this.index = e.target.value;
				this.isYearText = false;
			}
		}
	}
</script>

<style>
	.content{
		text-align: center;
	}
	.red{
		color: #FF0000;
	}
</style>
