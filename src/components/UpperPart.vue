<template>
	<div class="upper">
		<div class="upper_head">
			<div>
				<a class="logo" href=""><img src="../assets/index/appLOGO.png"></a>
				<div class="upper_search">
					<div class="search_ipt">
						<i class="iconfont icon-search"></i>
						<!-- placeholder 点击时消失 -->
						<input type="" name="" placeholder="ahc套装" onfocus="this.placeholder=''" onblur="this.placeholder='ahc套装'">
					</div>
					<div class="search_btn">
						<span></span>
					</div>
				</div>
				<a href="" class="search_car"><img src="../assets/index/car.png"><span>购物车</span></a>
			</div>
		</div>
		<div class="upper_mian">
			<div class="main_head">
				<div>
					<div class="head_icon">
						<i></i>
						<i></i>
						<i></i>
					</div>
					<span>所有分类</span>
				</div>
				<ul>
					<li><a href="">首页</a></li>
					<li><a href="">今日限时购</a></li>
					<li><a href="">国家馆</a></li>
					<li><a href="">海外旗舰店</a></li>
					<li><a href="">工厂店</a></li>
					<li><a href="">品质奶粉</a></li>
					<li><a href="">人气面膜</a></li>
					<li><a href="">充值</a></li>
				</ul>
			</div>
			<div class="mian_main">
				<div>
					<ul>
						<!-- 要动态生成什么标签，v-for就放在什么标签下，这里就放再li下，而不是ul -->
						<li v-for="(item,i) in mainData.data.body.frontCategoryList">
							<a href="">
								<i></i><span>{{item.categoryName}}</span><i></i>
							</a>
							<em></em>
						</li>
					</ul>
				</div>
			</div>
			<div class="main_foot">
				
			</div>
		</div>
	</div>	
</template>
<script type="text/javascript">
export default {
	name: 'upperPart',
	data() {
		return {
			mainData: null,
			users: null,
		}
	},
	mounted() {
		//this.getUserName();
		this.getMainData();
	},
	methods: {
		getUserName() {
			this.$axios
			.get('http://jsonplaceholder.typicode.com/users')
			.then(Response => {
				this.users = Response;
				//console.log(this.users);
			});
		},
		getMainData(){
			// 静态的json文件要记得放在static文件夹下
			const that = this;
			this.$axios.get('../../static/json/index/frontCategoryList.json')
			.then(function(res){
				that.mainData = res;
			  	console.log(res);
			})
			.catch(err=>{console.log(err)})
		}
	}
};
</script>
<!-- lang="scss" -->
<style type="text/css" lang="scss" scoped>
	.upper{

	}
	.upper_head{
		width: 1090px;
		margin: 0 auto;
		height: 100px;
		position: relative;
		& .upper_search {
			display: inline-block;
			margin-left: 150px;
		}
		&>div { height: 100%; }
	}
	.logo{ 
		position: absolute;
    	left: 0;
    	top: 17.5px; 
    }
    .upper_search {
    	
    	&>div {

    	}
    	& input {

    	}
    }
    .search_ipt{
    	border-radius: 24px 0 0 24px;
    	border: 2px solid red;
	    margin: 2px 1px;
	    padding: 6px 39px 6px 30px;
	    background-color: #fff;
	    width: 400px;
	    height: 23px;
	    position: relative;
	    top: 25px;
	    &>i {
	    	position: absolute;
		    left: 12px;
		    color: gray;
		    opacity: 0.6;
		    top: 5px;
	    }
	    &>input {
	    	width: 95%;
		    height: 25px;
		    border: none;
		    vertical-align: sub;
		    font-size: 13px;
	    }
    }
    .search_btn {
    	cursor: pointer;
    	background-color: #ff2337;	
    	background-image: linear-gradient(270deg,#ff2e64,#ff0003);
		float: right;
	    position: relative;
	    top: -16px;
	    right: -32px;
	    width: 60px;
	    height: 39px;
	    border-radius: 24px;
	    &>span {
	    	display: inline-block;
	    	width: 20px;
	    	height: 20px;
	    	background-image: url(../assets/index/search.png);
	    	position: relative;
    		top: 10px;
	    }
    }
    .search_btn:hover {
    	background: #ff2d59;
    	background-image: linear-gradient(270deg,#f85a7d,#ff3234);
    }
    .search_car {
    	display: inline-block;
	    position: relative;
	    top: 25px;
	    right: -80px;
	    height: 37px;
	    width: 106px;
	    border: 2px solid red;
	    border-radius: 24px;
	    &>span{
	    	color: #000;
	    	margin-top: 9px;
		    display: inline-block;
		    vertical-align: sub;
		    font-weight: bold;
		    padding-left: 10px;
		    font-size: 14px;
	    }
    }
    .search_car:hover {
    	background-color: #fff4f5;
    	&>span{ color: red; }
	}

	.main_head {
		width: 1090px;
		margin: 0 auto;
		color: #fff;
		font-size: 14px;
		height: 40px;
		&>div {
			float: left;
			width: 164px;
			background: linear-gradient(90deg,red,#ff3264);
			border-bottom: 1px solid #ff5160;
		}
		&>div,&>ul,& li { display: inline-block;height: 40px;line-height: 40px;float: left; }
		&>ul a {  color: #333;font-size: 15px;font-weight: 700; }
		&>ul a:hover { color: #ff1e32;text-decoration:none; }
		&>ul li:nth-child(1) {
			margin-left: 20px;
			&>a { color: #ff1e32; }
		}
		& li { overflow: hidden;padding: 0 20px; }
		& i {
			width: 15px;
		    height: 0;
		    border-top: 2px solid #ddd;
		    display: block;
		    margin-bottom: 3px;
		}
		&>div span {
			display: inline-block;
		    position: relative;
		    top: -15px;
		}
		& .head_icon {
			margin: 0 24px 0 15px;
			overflow: hidden;
			position: relative;
    		top: 14px;
		}
	}

	.mian_main {
		&>div {
			width: 1090px;
			margin: 0 auto;
		}
		& ul {
			width: 164px;
		}
		& ul>li { 
			height: 40px;
			line-height:40px;
			color: #fff;
			background: linear-gradient(90deg,red,#ff3264); 
		}
		& ul>li a {
			color: #fff;
			font-size: 14px;
		}
		& ul>li:hover {
			background: #fff;
			&>em { height: 0; }
			&>a { color: #ff1e32;text-decoration:none; }
		}
	}
	li>em {
		display: block;
	    position: relative;
	    bottom: 2px;
	    left: 5px;
	    width: 154px;
	    height: 1px;
	    background: #ff5160;
	    margin-top: -1px;
	}
</style>