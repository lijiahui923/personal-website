<template>
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
                        <div>登录</div>
                        <div>注册</div>
                    </div>
                </el-col>
            </el-row>
        </el-header>
        <slot></slot>
    </el-container>
</template>

<script>
/**
@description:头部
@createTime:2020-09-15
@create:lijiahui
*/
export default {
  name: 'top-header',
  props: {},
  components: {},
  data() {
    return {};
  },
  computed: {},
  watch: {},
  mounted() {},
  created() {},
  methods: {}
};
</script>
<style lang="scss" scoped>
.nav-header {
    width: 100%;
    min-height: 155px;
}
.nav {
    height: 60px;
    line-height: 60px;
}
.header-nav ul{
    display: flex;
    justify-content: space-around;
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
</style>
