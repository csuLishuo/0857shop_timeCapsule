<style lang="scss">
  @function px2rem($px) {
    //$px为需要转换的字号
    @return $px * 1 / 100 * 1rem;
  }
  .commentFeedback-container{
    .topBar{
      background: #fff;
      height: px2rem(100);
      padding: 0 px2rem(36);
      position: relative;
      line-height: px2rem(100);
      .left-box{
        width: px2rem(19);
        height: px2rem(37);
        position: absolute;
        left: px2rem(36);
        top: px2rem(32);
        img{
          width: 100%;
          height: 100%;
        }
      }
      .title{
        font-size: px2rem(32);
        font-weight: bold;
        text-align: center;
      }
    }
    .area-1{
      margin-top: px2rem(20);
      background: #fff;
      padding-left: px2rem(30);
      .line{
        .icon-box{
          width: px2rem(145);
        }
      }
    }
  }
</style>
<template>
  <div class="commentFeedback-container">
    <div class="topBar">
      <div class="left-box" @click="goBack"><img src="../images/icon39.png" alt=""></div>
      <div class="title">意见反馈</div>
    </div>
    <div class="area-1">
      <div class="form-box">
        <div class="line">
          <van-field
            type="tel"
            clearable
            placeholder="请输入手机号码"
          >
            <div class="icon-box" slot="left-icon">联系电话</div>
          </van-field>
        </div>
      </div>
    </div>
    <div class="area-1">
      <div class="form-box">
        <div class="line">
          <van-field
            type="textarea"
            clearable
            placeholder="意见反馈"
          >
          </van-field>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Toast } from 'vant'

export default {
  name: 'commentFeedback',
  components: {
  },
  data () {
    return {
      active: 0
    }
  },
  methods: {
    goBack () {
      this.$router.back(-1)
    },
    goDetail () {
      this.$router.push({
        name: 'detail_bargin'
      })
    },
    openPop () {
      this.showPop = true
    },
    test () {
      Toast.loading({
        mask: true,
        message: '加载中...'
      })
    }
  },
  mounted () {
    // this.test()
  },
  watch: {
  }
}
</script>
