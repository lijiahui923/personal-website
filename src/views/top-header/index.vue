<template>
<<<<<<< HEAD
    <el-container>
        <el-header class="nav-header">
            <el-row class="nav">
                <el-col :xs="0" :sm="10" :md="10" :lg="10">
                    <div class="header-nav">
                        <ul>
                            <li><svg-icon icon-class="main"></svg-icon>主站</li>
                            <li><svg-icon icon-class="nav"></svg-icon>个人导航</li>
                            <li><svg-icon icon-class="document"></svg-icon>文档系统</li>
                            <li><svg-icon icon-class="weibo"></svg-icon>微博</li>
                            <li><svg-icon icon-class="iphone"></svg-icon>下载APP</li>
                        </ul>
                    </div>
                </el-col>
                <el-col :xs="18" :sm="10"  :md="10" :lg="10">
                    <div class="header-input">
                        <el-input placeholder="请输入内容">
                            <el-button slot="append" icon="el-icon-search"></el-button>
                        </el-input>
                    </div>
                </el-col>
                <el-col :xs="6" :sm="4" :md="4" :lg="4">
                    <div class="header-user">
                        <a href="#" class="headphoto">
                            <img src="../../assets/images/headphoto.png"/>
                        </a>
                        <router-link to="/login">登录</router-link>
                        <div>注册</div>
                    </div>
                </el-col>
            </el-row>
        </el-header>
        <slot></slot>
    </el-container>
=======
  <el-header class="nav-header" :class="[]">
        <el-row class="nav">
            <el-col :md="10" :lg="10" :xl="10">
                <div class="hidden-sm-and-down header-nav">
                    <ul>
                        <li><svg-icon icon-class="main"></svg-icon>主站</li>
                        <li><svg-icon icon-class="nav"></svg-icon>个人导航</li>
                        <li><svg-icon icon-class="document"></svg-icon>文档系统</li>
                        <li><svg-icon icon-class="weibo"></svg-icon>微博</li>
                        <li><svg-icon icon-class="iphone"></svg-icon>下载APP</li>
                    </ul>
                </div>
            </el-col>
            <el-col :md="10" :lg="10" :xl="10">
                <div class="hidden-sm-and-down header-input">
                    <el-input placeholder="请输入内容">
                        <el-button slot="append" icon="el-icon-search"></el-button>
                    </el-input>
                </div>
            </el-col>
            <el-col :md="4" :lg="4" :xl="4">
                <div class="hidden-sm-and-down header-user">
                    <a href="#" class="headphoto">
                        <img src="../../assets/images/headphoto.png"/>
                    </a>
                    <div>登录</div>
                    <div>注册</div>
                </div>
            </el-col>
            <el-col :xs="12" :sm="12" :md="0" :lg="0" :xl="0"><div class="grid-content bg-purple-light">logo</div></el-col>
            <el-col :xs="12" :sm="12" :md="0" :lg="0" :xl="0"><div class="grid-content bg-purple"></div>hah</el-col>
        </el-row>
    </el-header>
>>>>>>> ce6b02301e2ddeb6b10134d38b92c5c898e92381
</template>

<script>
/**
@description:头部导航栏
@createTime:2020-09-16
@create:lijiahui
*/
export default {
  name: 'top-header',
  props: {},
  components: {},
  data() {
    return {
        scrollTop: 0
    };
  },
  computed: {},
  watch: {},
  mounted() {},
  created() {
      window.addEventListener('scroll', ()=>{
        //   获取滚动条的位置
        this.scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop;
        if (this.scrollTop > 200) {
            document.querySelector('.nav-header').classList.add('sticky');
        } else if (this.scrollTop === 0) {
            document.querySelector('.nav-header').classList.remove('sticky');
        }
    })
  },
  methods: {}
};
</script>
<style lang="scss" scoped>
.nav-header {
    width: 100%;
    position: relative;
    z-index: 1;
}
.nav {
    height: 60px;
    line-height: 60px;
}
.header-nav ul{
    display: flex;
    justify-content: space-around;
    font-size: 14px;
    font-weight: 600;
    color: #666;
}
.header-user {
    display: flex;
    justify-content: space-around;
}
.header-user{
    & img {
        margin-top: 10px;
    }
    & a,img {
        height: 40px;
        width: 40px;
        border-radius: 50%;
    }
}
.sticky {
    position: fixed;
    top: 0;
    background: #fff;
}
</style>
