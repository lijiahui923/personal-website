<template>
  <el-aside class="aside-right">
      <div class="right-conent">
          <h3 class="right-title">公告栏</h3>
          <p class="right-decs">
              目前系统还在开发中~并不是稳定版本，还希望大家积极反馈bug
          </p>
      </div>
      <div class="right-conent">
          <h3 class="right-title">更多功能</h3>
          <div class="right-more">
              <ul class="more-link">
                  <li class="more-link-item"><a href="#"><svg-icon icon-class="diary"></svg-icon>日记</a></li>
                  <li class="more-link-item"><a href="#"><svg-icon icon-class="sponsors"></svg-icon>赞助博主</a></li>
                  <li class="more-link-item"><a href="#"><svg-icon icon-class="uphand"></svg-icon>友人帐</a></li>
                  <li class="more-link-item"><a href="#"><svg-icon icon-class="devil"></svg-icon>我的追番</a></li>
                  <li class="more-link-item"><a href="#"><svg-icon icon-class="communication"></svg-icon>弹幕留言墙</a></li>
                  <li class="more-link-item"><a href="#"><svg-icon icon-class="douban"></svg-icon>我的豆瓣</a></li>
                  <li class="more-link-item"><a href="#"><svg-icon icon-class="project"></svg-icon>我的项目</a></li>
                  <li class="more-link-item"><a href="#"><svg-icon icon-class="Introduction"></svg-icon>个人简介</a></li>
              </ul>
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
  name: 'aside-right',
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
.aside-right {
    width: 100% !important;
}
.right-conent {
    background: #fff;
    padding: 20px;
    border-radius: 5px;
    margin-bottom: 20px;
    & .right-title {
        font-size: 18px;
        font-weight: 600;
        padding: 10px 10px 20px;
        border-bottom: 1px solid #666;
    }
    & .right-decs {
        padding-top: 20px;
        font-size: 18px;
    }
}
.more-link {
    display: flex;
    flex-wrap: wrap;
    margin-top: 10px;
    & .more-link-item {
        width: 50%;
        height: 60px;
        font-size: 18px;
        font-weight: 600;
    }
}
</style>
