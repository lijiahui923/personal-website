<template>
<<<<<<< HEAD
    <div class="home">
		<router-view />
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
=======
    <el-container direction="vertical">
		<div class="bg"></div>
		<topHeader/>
		<el-container direction="vertical" class="center-content">
			<el-row>
				<el-col :sm="8" :md="5" :lg="5" :xl="5"><div class="hidden-xs-only"><asideLeft/></div></el-col>
				<el-col :xs="24" :sm="16" :md="14" :lg="14" :xl="14"><mainWapper/></el-col>
				<el-col :md="5" :lg="5" :xl="5"><div class="hidden-sm-and-down"><asideRight/></div></el-col>
			</el-row>
		</el-container>
	</el-container>
>>>>>>> ce6b02301e2ddeb6b10134d38b92c5c898e92381
</template>
<script>
import topHeader from './../top-header';
import asideLeft from './../aside-left';
import mainWapper from './../main-wapper';
import asideRight from './../aside-right';
export default {
    name: "Index",
    components: { topHeader, asideLeft, mainWapper, asideRight },
    data(){
        return {}
    },
    computed: {},
    mounted(){},
    watch: {}
}
</script>
<style lang="scss">
<<<<<<< HEAD
	.home {
		@include webkitA(background,linear-gradient(to top, #d299c2, #fef9d7));
	}
	.main {
		min-height: 700px;
		margin: 25px 20px 78px 20px;
	}
	.bg {
		// background: url(../../assets/images/tKb5.jpg);
		// background-size: cover;
		// background-repeat: no-repeat;
		// background-position: 100% 100%;
		// position: fixed;
		// z-index: -1;
		// top: 0;
		// left: 0;
		// right: 0;
		// bottom: 0;
	}
	
=======
.center-content {
	margin: 0 20px;
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
>>>>>>> ce6b02301e2ddeb6b10134d38b92c5c898e92381
</style>