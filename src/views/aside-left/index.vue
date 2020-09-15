<template>
  <div>
      <el-aside class="aside-left">
        <div class="user-info">
            <div class="user-bg"></div>
            <div class="user-photo">
                <!-- <a class="user-photo-border">
                    <span><img src="../../assets/images/headphoto.png"/></span>
                </a> -->
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
                <span class="user-other-link-item">1</span>
                <span class="user-other-link-item">1</span>
                <span class="user-other-link-item">1</span>
                <span class="user-other-link-item">1</span>
                <span class="user-other-link-item">1</span>
                <span class="user-other-link-item">1</span>
            </div>
            </div>
        </div>
    </el-aside>
  </div>
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
