<template>
	<div>
		<!-- template下只能有一级div -->
		<Header ref='header'></Header>
		<UpperPart ref='upper-part'></UpperPart>
		<div>{{msg}}</div>

	</div>
</template>
<script>
import Header from './Header';
import UpperPart from './UpperPart';

export default {
	name: 'index',
	data(){
		return {
			msg: '欢迎来到我的考拉海购。'
		}
	},
	components:{
		// 子组件名必须大写开头
		Header,
		UpperPart
	}
};
</script>
<style type="text/css" scpped>
	
</style>