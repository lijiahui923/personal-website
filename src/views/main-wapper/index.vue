<template>
    <el-container class="mian-part">
        <el-main　class="conent">
            <div class="conent-header">
                <div class="conent-header-left">
                    <svg-icon icon-class="home"></svg-icon>
                    <span>首页</span>
                </div>
                <div class="conent-header-right">
                    <ul>
                        <li>硬件奇谈<span>29</span></li>
                        <li>个人日常<span>29</span></li>
                        <li>个人项目<span>29</span></li>
                        <li>程序人生<span>29</span></li>
                        <li>各种折腾<span>29</span></li>
                        <li>使用内容<span>29</span></li>
                    </ul>
                </div>
            </div>
            <div class="content-panel">
                <div class="panel-wrapper">
                    <h4 class="panel-title">go Echo框架集成Swagger 自动生成api文档</h4>
                    <div class="is-hidden">
                        <p class="pancel-desc">
                            之前的api文档一直都是手写的，使用起来非常麻烦，所以我打算采用swagger来自动生成api文档，
                            减少我的工作量同时接口更新后文档也能自动更新，减少自己维护文档的麻烦，废话不多说，直接开始集成。
                        </p>
                        <div　class="panel-footer">
                            <span class="panel-footer-time"><svg-icon icon-class="time"></svg-icon>2020-09-15</span>
                            <span class="panel-footer-comments"><svg-icon icon-class="comments"></svg-icon>23评论</span>
                            <span class="panel-footer-read"><svg-icon icon-class="detail"></svg-icon>23阅读</span>
                            <span class="panel-footer-givelove"><svg-icon icon-class="givelike"></svg-icon>12人点赞</span>
                        </div>
                    </div>
                </div>
            </div>
        </el-main>
        <el-footer>
            <el-pagination
            background
            layout="prev, pager, next"
            :total="1000">
            </el-pagination>
        </el-footer>
    </el-container>
</template>

<script>
/**
@description:
@createTime:2020-09-15
@create:lijiahui
*/
export default {
  name: 'main-wapper',
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
.mian-part {
    text-align: center;
}
.conent {
    min-height: 700px;
    padding: 0 20px;
    width: 100%;
    & .conent-header {
        padding: 10px 0;
        background: #fff;
        display: flex;
        border-radius: 5px;
        height: 68px;
        & .conent-header-left {
            display: flex;
            flex-direction: column;
            justify-content: center;
            padding: 0 20px;
            border-right: 1px solid rgba(32, 30, 30, 0.1);
            & span {
                margin-top: 10px;
            }
        }
        & .conent-header-left > svg {
            width: 3.2em;
        }
        & .conent-header-right ul{
            height: 68px;
            display: flex;
            flex-wrap: wrap;
            & li {
                    height: 30px;
                    line-height: 30px;
                    padding: 0 12px;
                & span {
                    background: #ddd;
                    padding: 0 15px;
                    margin: 5px;
                }
            }
        }
    }
    & .content-panel {
        position: relative;
        color: #fff;
        height: 420px;
        border-radius: 10px;
        background: url('./../../assets/images/img459.jpg') center center;
        background-repeat: no-repeat;
        margin: 20px 0;
        & .panel-wrapper {
            position: absolute;
            left: 0;
            bottom: 0;
        }
        & .panel-wrapper:hover>.is-hidden{
            visibility: unset;
        }
        & .panel-title {
            font-size: 22px;
            font-weight: 700;
            margin: 40px 0;
        }
        & .pancel-desc {
            width: 80%;
            margin: 0 auto;
            font-size: 18px;
            line-height: 30px;
        }
        & .panel-footer {
            border-top: 1px solid rgba(255,255,255,.1);
            padding-top: 10px;
            display: flex;
            justify-content: space-around;
            margin: 10px;
            font-size: 18px;
            font-weight: 500;
        }
    }
}
.is-hidden {
    visibility: hidden;
}
</style>
