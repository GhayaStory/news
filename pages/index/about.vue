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
		<view class="uni-title uni-common-pl">多列选择器</view>
		<view class="uni-list">
			<view class="uni-list-cell">
				<view class="uni-list-cell-left">
					当前选择
				</view>
				<view class="uni-list-cell-db">
					<picker mode="multiSelector" @columnchange="cloumChange" :value="showIndex" :range="showData">
						<view class="uni-input">
						{{showData[showIndex[0]].name}}，
						{{showData[showIndex[0]].value[showIndex[1]].name}}，
						{{showData[showIndex[0]].value[showIndex[1]].value[showIndex[2]]}}
						</view>
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
	var allData = [];
	var showData = [];
	let _self;
	export default {
		data() {
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
				showIndex:[0,0,0],
				showData:[[],[],[]]
			}
		},
		onLoad() {
			_self = this;
			console.log(this);
			console.log(this.showIndex);
			initData();
			function initData(){
				allData = [
					{
						name:"R1",
						value:[
							{name:"1",value:['1','2','3','4','5']},
							{name:"2",value:['1','2','3']},
							{name:"3",value:['1','2','3','4','5','6']}
						],
					},
					{
						name:"R2",
						value:[
							{name:"1",value:['1','2','3','4']},
							{name:"2",value:['1','2','3']},
							{name:"3",value:['1','2','3','4','5','6']},
							{name:"4",value:['1','2','3','4']},
							{name:"5",value:['1','2','3','4','5']}
						]
					}
				]
				console.log(_self);
				// let arrOne = dataToArr(allData);
				// let arrTwo = dataToArr(allData[_self.showIndex[0]].value);
				// let arrThree = dataToArr(allData[_self.showIndex[0]].value[_self.showIndex[1]]);
				
				// function dataToArr(data){
				// 	let arr = [];
				// 	for(let item of data){
				// 		if(item.name){
				// 			arr.push(item.name);
				// 		}else{
				// 			arr.push(item);
				// 		}
				// 	}
				// 	return arr;
				// }
				// _self.showData = [arrOne,arrTwo,arrThree];
				
				// console.log(showData[this.showIndex[0]].name);
			}
		},
		methods:{
			dateChange:function(e){
				this.index = e.target.value;
				this.isYearText = false;
			},
			cloumChange:function(e){
				console.log(e);
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
