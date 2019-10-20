<template>
	<div id="header">
		<div>
			<div class="header_left">
				<span>考拉欢迎你！</span>
				<router-link to="/Login" tag="a"><i>登录</i></router-link>
				<router-link to="/Login" tag="a"><i>免费注册</i></router-link>
				<a href="" class="appMa" @mouseover="showMa = !showMa" @mouseout="showMa = !showMa">手机考拉
					<span class="m-notice" v-if="showMa"><img src="../assets/index/appMa.png">
						<strong>下载APP<br>领1000元新人礼包</strong>
						<span class="arrow">
							<span class="arr"></span>
							<span class="arr1"></span>
						</span>
					</span>
				</a>
			</div>
			<div class="header_right">
				<a href="">每日签到</a>
				<a href="">我的订单</a>
				<!--  -->
				<div @mouseenter="grzx=true" @mouseleave="grzx=false">
					<a class="topNavHolder" href="">
						个人中心
						<i class='arr'></i>
					</a>
					<div id="grzx" v-if="grzx" class="xiala">
						<ul>
							<li><router-link to="" tag="a"><i>我的优惠券</i></router-link></li>
							<li><router-link to="" tag="a"><i>我的红包</i></router-link></li>
							<li><router-link to="" tag="a"><i>我的考拉豆</i></router-link></li>
							<span></span>
							<li><router-link to="" tag="a"><i>账号管理</i></router-link></li>
							<li><router-link to="" tag="a"><i>我的实名认证</i></router-link></li>
							<li><router-link to="" tag="a"><i>我的发票抬头</i></router-link></li>
							<span></span>
							<li><router-link to="" tag="a"><i>我收藏的商品</i></router-link></li>
							<li><router-link to="" tag="a"><i>我关注的品牌</i></router-link></li>
							<span></span>
							<li><router-link to="" tag="a"><i>售后管理</i></router-link></li>
						</ul>
					</div>	
				</div>
				<div @mouseenter="khfw=true" @mouseleave="khfw=false">
					<a class="topNavHolder" href="">
						客户服务
						<i class='arr'></i>
					</a>
					<div id="khfw" v-if="khfw" class="xiala">
						<ul>
							<li><i class="iconfont icon-unie737"></i><router-link to="" tag="a"><i>联系客服</i></router-link></li>
							<li><i class="iconfont .icon-bangzhu"></i><router-link to="" tag="a"><i>帮助中心</i></router-link></li>
							<li><i class="iconfont icon-zhishichanquanguanli"></i><router-link to="" tag="a"><i>知识产权保护</i></router-link></li>
							<li><i class="iconfont icon-warn"></i><router-link to="" tag="a"><i>规则中心</i></router-link></li>
						</ul>
					</div>	
				</div>
				<div @mouseenter="czzx=true" @mouseleave="czzx=false">
					<a class="topNavHolder" href="">
						充值中心
						<i class='arr'></i>
					</a>
					<div id="czzx" v-if="czzx" class="xiala">
						<ul>
							<li><i></i><router-link to="" tag="a"><i>话费充值</i></router-link></li>
							<li><i></i><router-link to="" tag="a"><i>游戏充值</i></router-link></li>
							<li><i></i><router-link to="" tag="a"><i>AppStore充值卡</i></router-link></li>
						</ul>
					</div>	
				</div>
				<div @mouseenter="xfzqy=true" @mouseleave="xfzqy=false">
					<a class="topNavHolder" href="">
						消费者权益
						<i class='arr'></i>
					</a>
					<div id="xfzqy" v-if="xfzqy" class="xiala">
						<ul>
							<li><i></i><router-link to="" tag="a"><i>消费者告知书</i></router-link></li>
						</ul>
					</div>	
				</div>
				<div @mouseenter="gd=true" @mouseleave="gd=false">
					<a class="topNavHolder" href="">
						更多
						<i class='arr'></i>
					</a>
					<div id="gd" v-if="gd" class="xiala">
						<ul>
							<li><router-link to="" tag="a"><i>收藏本站</i></router-link></li>
							<span></span>
							<li><router-link to="" tag="a"><i>新浪微博</i></router-link></li>
							<li><router-link to="" tag="a"><i>微信公众号</i></router-link></li>
							<li><router-link to="" tag="a"><i>招商合作</i></router-link></li>
						</ul>
					</div>	
				</div>
			</div>
		</div>
	</div>
</template>
<style lang='scss' scoped>

	$color:#fff;
	$color1:#999;
	#header {
		color:$color1; 
		background: #000; 
    	height: 30px;
    	line-height: 30px;
    	&>div{
    		width: 1090px;
			margin: 0 auto;
    	}
	}
	/* 重复style代码块 */
	@mixin headMargin{  margin-left: 20px; }

	.header_left a,.header_right a { text-decoration: none; display: inline-block; }
	.header_left {
		float: left; 
		&>a{ @include headMargin }
		&>a:hover{ color:$color; }
	}
	.header_right {
		float:right;
		&>div{ display: inline-block;position:relative; }
		&>div>a:hover{ color: #ff1e32; }
		&>div:hover { background: $color; }
		&>a{ display: inline-block;padding: 0 14px 0 8px; }
		&>a:hover{ color:$color; }
	}
	.header_right>div:hover .topNavHolder>.arr { border-top-color: #ff1e32; }
	.header_right>div:hover .topNavHolder>.arr{ transform: rotate(180deg);}
	a:-webkit-any-link{color:$color1;}

	.appMa { position: relative; }
	.header_left .m-notice {
		position: absolute;
	    top: 38px;
	    left: -45px;
	    line-height: 18px;
	    padding: 5px 5px 0;
	}
	.header_left .m-notice>strong {
		padding: 4px 0;
	}
	.header_left .arrow {
		position: absolute;
	    top: 0;
	    right: auto;
	    left: 56px;
	    transform: rotate(-90deg);
	    &arr1,&arr {
	    	position: absolute;
		    left: 0;
		    border-width: 8px;
		    border-style: dashed dashed solid;
		    width: 0;
		    height: 0;
		    font-size: 0;
	    	top: -15px;
    		border-color: transparent transparent #fff;
	    }
	    &arr {
	    	top: -16px;
    		border-color: transparent transparent #e4e4e4;
	    }
	}

	.xiala {
		border-top: 0;
    	box-shadow: 0 1px 1px rgba(0,0,0,.12);
		position: absolute;
	    background: #fff;
	    text-align: left;
	    padding: 5px 15px 10px 15px;
	    width: 85px;
	    z-index: 1;
	    & li>a:hover { color: red; }
	    &>ul>span { display:block; width: 100%;height: 1px; background: #eaeaea; }
	}
	#grzx {
	    width: 85px;
	}
	#khfw,#czzx { width: 100px;padding: 5px 0px 10px 15px; }
	#gd {
		width: 65px;
		left: -31px;
	}
</style>
<script type="text/javascript">
export default{
	// header 是html里的标签，不能用于name
	// 标签调用函数  @mouseenter
	// 导航下拉： @mouseenter  @mouseleave
	name: 'Header',
	data(){
		return {
			showMa: false,
			grzx: false,
			khfw: false,
			czzx: false,
			xfzqy: false,
			gd: false
		}
	},
	
	methods:{
		
	},
	watch: {
		
	}
}
</script>

