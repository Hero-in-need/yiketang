<template>
	<view class="content">
		<u-picker v-model="show" mode="selector" :default-selector="[0]" :range="studentsNumber"  :confirm-text="text" @confirm="changeMessage"></u-picker>
		<u-popup v-model="showModify" mode="bottom"  height="50%">
			<view style="text-align: center">
			<h3>{{title1}}</h3>
			<h3>{{title2}}</h3>
			<h3>{{title3}}</h3>
			</view>
			<view style="width:80%;margin:0px auto">
			<u-input v-model="numberModify" type="text" border placeholder="学号修改" cursor-spacing='200'/>
			<u-input v-model="nameModify" type="text" border placeholder="姓名修改" cursor-spacing='150'/>
			<u-input v-model="classModify" type="text" border placeholder="班级修改" cursor-spacing='150'/>
			<u-button @tap="submit" style="margin-top:20px" type="primary">确定</u-button>
			</view>
	    </u-popup>
		<view style="margin-top:20px">
		<u-button style="float:right;" @click="show = true" type="error" @tap="deleteMessage">删除</u-button>
		<u-button style="float:right;"  type="warning" @tap="modify">修改</u-button>
		<u-toast ref="uToast" />
		</view>
		<u-popup v-model="showSearch" mode="bottom"  height="60%">
		<view style="width:80%;margin:10px auto">
		<u-search placeholder="请输入需要查询的学号" v-model="keyNumber" shape="square" @custom="search"></u-search>
		</view>
		 </u-popup>
		<view v-for="(student,index) in students">
				<view class="iconfont icon-yewutubiao_xueshengchaxun" style="font-size:100px;color:#ff9900;float:left;padding-left:10%"></view>
				<view style="float: left">
					<h1>ID:<span style="color:#dd6161">{{index}}</span></h1>
					<h2>学号:<span style="color:#f29100">{{student.number}}</span></h2>
					<h2>姓名:<span style="color:#f29100">{{student.name}}</span></h2>
					<h2>班级:<span style="color:#f29100">{{student.class}}</span></h2>
				</view>
			</view>
			<view class="searchIcon">
			<u-icon name="search" color="white" size="47px" @tap="searchYemian"></u-icon>
			</view>
	</view>
</template>

<script>
	export default {
		props:["state"],
		data() {
			return {
				showSearch:false,
				mode: 'square',
				scrollTop: 0,
				iconStyle: {
					fontSize: '32rpx',
					color: '#2979ff'
				},
				keyNumber: null,
				title1:null,
				title2:null,
				title3:null,
				operation:'',
				text:'',
				show: false,
				showModify:false,
				nameModify:null,
				numberModify:null,
				classModify:null,
				studentsNumber:[],
				students:[{
					number:5120184430,
					class:'物联1802',
					name:'曾维鹏'
				},{
					number:5120184510,
					class:'电子1801',
					name:'徐锐'
				},{
					number:5120184470,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184480,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184490,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184425,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184431,
					class:'自动1804',
					name:'袁家钱'
				}]
			       }
              },
			  watch: {
					state(val){
						if(val==0){
						this.students=[{
					number:5120184430,
					class:'物联1802',
					name:'曾维鹏'
				},{
					number:5120184510,
					class:'电子1801',
					name:'徐锐'
				},{
					number:5120184470,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184480,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184490,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184425,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184431,
					class:'自动1804',
					name:'袁家钱'
				}]
				  for(var i=0;i<this.students.length;i++)		
				  {
					this.studentsNumber[i]=this.students[i].number
				  }
				  this.studentsNumber.splice(i,9999)
						}
						 if(val==1){
						this.students=[{
					number:5120184430,
					class:'物联1802',
					name:'机器人'
				},{
					number:5120184530,
					class:'电子1801',
					name:'徐锐'
				},{
					number:5120184440,
					class:'自动1804',
					name:'袁家钱'
				}]
				for(var i=0;i<this.students.length;i++)
				{
					this.studentsNumber[i]=this.students[i].number
				}
				this.studentsNumber.splice(i,9999)
								  }
				else if(val==2){
						this.students=[{
					number:5120184370,
					class:'物联1802',
					name:'迟到了啊'
				},{
					number:5120184230,
					class:'电子1801',
					name:'徐锐'
				},{
					number:5120184110,
					class:'自动1804',
					name:'袁家钱'
				},{
					number:5120184589,
					class:'自动1804',
					name:'袁家钱'
				}]
				for(var i=0;i<this.students.length;i++)
				{
					this.studentsNumber[i]=this.students[i].number
				}
				this.studentsNumber.splice(i,9999)
				}
					}	
		      },
			  onPageScroll(e) {
			  	this.scrollTop = e.scrollTop;
			  },
			  methods:{		
                 searchYemian(){
					 this.showSearch=true;
				 },
				 search(){
					 var arr=[{number:null,name:null,class:null}];
                    for(var i=0;i<this.studentsNumber.length;i++)
					{
						if(this.keyNumber==this.studentsNumber[i])
						{
							arr[0].number=this.students[i].number
							arr[0].name=this.students[i].name
							arr[0].class=this.students[i].class
							this.studentsNumber[0]=arr[0].number
							this.studentsNumber.splice(1 ,9999)
							break;
						}
				    }
					if(arr[0].number==null){
						this.$refs.uToast.show({
							title: '无该学生信息',
							type: 'error',
						})
						console.log(this.keyNumber)
						this.keyNumber=null
					}
					else{
						this.students=arr;
						this.keyNumber=null
						console.log(this.students)
					}
				 },
				 changeMessage(value){
					 if(this.text=="删除"){
					this.operation=value[0] 
					this.students.splice(value[0], 1);
					this.studentsNumber.splice(value[0] ,1)
					}
					if(this.text=="修改"){
					this.showModify=true
					this.operation=value[0]
					this.title1=this.students[value[0]].number
					this.title2=this.students[value[0]].name
					this.title3=this.students[value[0]].class
					// delete this.students[0].number;
					// delete this.students[0].class;
					// delete this.students[0].name;
					}
				  },
				 submit(){
					 if(this.numberModify!=null){this.students[this.operation].name=this.numberModify;}
					 if(this.nameModify!=null){this.students[this.operation].number=this.nameModify;}
					 if(this.classModify!=null){this.students[this.operation].class=this.classModify;}
					 this.showModify=false
				 },
				 deleteMessage(){
					 this.text="删除";
					 this.show = true;
				 },
	             modify(){
					 this.text="修改";
					 this.show = true;
	             }
			  },
			  mounted(){
				  for(var i=0;i<this.students.length;i++)		
				  {
					this.studentsNumber[i]=this.students[i].number
				  }
				  this.studentsNumber.splice(i,9999)
				  console.log(this.studentsNumber)
			  },
	}
</script>

<style  scoped>
	.content {
		display: flex;
		flex-direction: column;
		background-color: #82848a;
	}
	.searchIcon{
		width: 50px;height: 50px;border:1px sold transparent ;border-radius:50%;background-color: #18B566;line-height:25px;position:fixed;bottom: 30px;right: 4.5%;
	}
</style>
