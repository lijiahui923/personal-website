<template>
    <el-aside class="aside-left">
        <div class="user-info">
            <div class="user-bg"></div>
            <div class="user-photo">
                <span class="user-photo-border">
                    <img src="../../assets/images/headphoto.png" />
                </span>
            </div>
            <div class="user-name">我会瘦的</div>
            <div class="user-statistical">
                <ul>
                    <li>
                        <span class="user-statistical-num">175</span>
                        <span class="user-statistical-title">文章</span>
                    </li>
                    <li>
                        <span class="user-statistical-num">175</span>
                        <span class="user-statistical-title">文章</span>
                    </li>
                    <li>
                        <span class="user-statistical-num">175</span>
                        <span class="user-statistical-title">文章</span>
                    </li>
                </ul>
            </div>
            <div>
            <div class="user-other-link">
                <span class="user-other-link-item"><svg-icon icon-class="github"></svg-icon></span>
                <span class="user-other-link-item"><svg-icon icon-class="barrage"></svg-icon></span>
                <span class="user-other-link-item"><svg-icon icon-class="bird"></svg-icon></span>
                <span class="user-other-link-item"><svg-icon icon-class="zhihu"></svg-icon></span>
                <span class="user-other-link-item"><svg-icon icon-class="steam"></svg-icon></span>
                <span class="user-other-link-item"><svg-icon icon-class="bilibili"></svg-icon></span>
            </div>
            </div>
        </div>
    </el-aside>
</template>

<script>
/**
@description:
@createTime:2020-09-15
@create:lijiahui
*/
export default {
  name: 'aside-left',
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
.aside-left {
    width: 22%;
    text-align: center;
}
.user-info {
    width: 100%;
    background: #fff;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    position: relative;
}
.user-bg {
    height: 120px;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    background: url(../../assets/images/y0qR.png) center center no-repeat;
}
.user-photo {
    height: 52px;
}
.user-photo-border {
    display: inline-block;
    width: 90px;
    height: 90px;
    position: absolute;
    left: 50%;
    transform: translate(-50%,-50%);
    transition: transform .2s;
    border-radius: 50%;
    border: 5px solid rgba(255, 255, 255, .5);
    & img {
        width: 90px;
        height: 90px;
        border-radius: 50%;
    }
}
.user-photo-border:hover {
    transform: translate(-50%,-50%) rotateZ(360deg);
    width: 130px;
    height: 130px;
    & img {
        width: 130px;
        height: 130px;
    }
}
.user-statistical {
    font-size: 18px;
    & ul {
        display: flex;
    }
    & ul li {
        display: flex;
        flex-direction: column;
        flex: 1;
    }
    & .user-statistical-num {
        line-height: 50px;
        font-weight: 700;
        color: #00a1d6;
    }
    & .user-statistical-title {
        line-height: 20px;
        color: #000;
    }
}
.user-other-link {
        padding: 20px 0;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    & .user-other-link-item {
        width: 55px;
        height: 55px;
        background-color: #eee;
        border-radius: 50%;
        margin: 2px;
        line-height: 55px;
    }
}
.user-name {
    margin: 20px 0;
}
</style>
