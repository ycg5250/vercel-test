<template>
  <div class="block-content">
    <div class="title-wrap">
      <span>带宽</span>
      <span>(0.1561 kb/TRX)</span>
    </div>
    <div class="container">
      <div class="progress">
        <div class="value" :style="{ width: '50%' }"></div>
      </div>
      <div class="available">
        <span>{{ $t('available') }}: 1.47 KB / 4.47 KB</span>
      </div>
      <div class="detail">
        <div class="freeze-wrap">
          <div class="freeze">{{ $t('freeze') }}:</div>
          <div class="freeze freeze-2">1087 TRX</div>
        </div>
        <div class="mortgage-wrap">
          <div class="mortgage">{{ $t('mortgage_0') }}: 105.24 TRX</div>
          <div class="mortgage">{{ $t('mortgage_1') }}: 105.24 TRX</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
    },
  },
};
</script>

<style lang="scss" scoped>
.block-content {
  .mt {
    margin-top: 0.48rem;
  }
  .title-wrap {
    display: flex;
    align-items: center;
    span {
      font-size: 0.32rem;
      font-family: PingFang SC, PingFang SC-Medium;
      font-weight: 500;
      color: #3a3b3d;
    }
    :nth-child(2) {
      margin-left: 0.16rem;
      font-size: 0.26rem;
      font-family: PingFang SC, PingFang SC-Regular;
      font-weight: 400;
      color: #9ea0a5;
    }
  }
  .container {
    margin-top: 0.23rem;
    background: #ffffff;
    border-radius: 0.24rem;
    padding: 0.32rem;
    .progress {
      margin-top: 0.23rem;
      position: relative;
      width: 100%;
      height: 0.4rem;
      background: #ebf4ff;
      border-radius: 0.18rem;
      .value {
        position: absolute;
        left: 0;
        top: 50%;
        transform: translateY(-50%);
        height: 0.4rem;
        line-height: 0.4rem;
        background: #2980fe;
        border-radius: 0.18rem;
        font-size: 0.12rem;
        font-family: PingFangSC, PingFangSC-Regular;
        font-weight: 400;
        text-align: center;
        color: #ffffff;
      }
    }
    .available {
      display: flex;
      align-items: center;
      span {
        margin-top: 0.08rem;
        font-size: 0.22rem;
        font-family: PingFang SC, PingFang SC-Regular;
        color: #9ea0a5;
        line-height: 0.22rem;
      }
    }
    .detail {
      margin-top: 0.22rem;
      background: #f2f4f7;
      border-radius: 0.2rem;
      padding: 0.24rem;
      .freeze-wrap {
        display: flex;
        align-items: center;
        .freeze {
          font-size: 0.26rem;
          color: #3a3b3d;
          font-family: PingFang SC, PingFang SC-Medium;
          font-weight: 500;
        }
        .freeze-2 {
          margin-left: 0.1rem;
          font-family: PingFang SC, PingFang SC-Semibold;
          font-weight: 600;
        }
      }
      .mortgage-wrap {
        margin-top: 0.08rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        .mortgage {
          font-size: 0.24rem;
          font-family: PingFang SC, PingFang SC-Regular;
          color: #9ea0a5;
          font-weight: 400;
        }
      }
    }
  }
}
</style>
