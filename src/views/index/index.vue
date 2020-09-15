<template>
    <div>
		<topHeader>
			<el-container class="main">
				<div class="bg"></div>
				<asideLeft　/>
				<mainConent />
				<asideRight/>
			</el-container>
			<botomFooter/>
		</topHeader>
    </div>
</template>
<script>
import topHeader from './../top-header';
import asideLeft from './../aside-left';
import mainConent from './../main-conent';
import asideRight from './../aside-right';
import botomFooter from './../botom-footer';
export default {
    name: "Index",
    components: { topHeader, asideLeft, mainConent, asideRight, botomFooter },
    data(){
        return {}
    },
    computed: {},
    mounted(){},
    watch: {}
}
</script>
<style lang="scss">
	.main {
		min-height: 700px;
		margin: 25px 20px 78px 20px;
	}
	.bg {
		background: url(../../assets/images/tKb5.jpg);
		background-size: cover;
		background-repeat: no-repeat;
		background-position: 100% 100%;
		position: fixed;
		z-index: -1;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
	}
	
</style>