<template>
  <div class="home">
    <BlockContent />
    <BlockContent />
    <div class="tab-wrap">
      <div class="tab" :class="{ active: tabIndex === 0 }" @click="onTab(0)">
        {{ $t('freeze') }}
      </div>
      <div
        class="tab tab-2"
        :class="{ active: tabIndex === 1 }"
        @click="onTab(1)"
      >
        {{ $t('removeFreeze') }}
      </div>
    </div>
    <div class="freeze-content">
      <div class="select-title">
        <span>{{ $t('freezeTitle') }}</span>
        <span>{{ $t('freezeDesc') }}</span>
      </div>
      <div class="select-button">
        <div
          class="button"
          :class="{ active: btnIndex === 0 }"
          @click="onBtn(0)"
        >
          {{ $t('bandwidth') }}
        </div>
        <div
          class="button button-2"
          :class="{ active: btnIndex === 1 }"
          @click="onBtn(1)"
        >
          {{ $t('energy') }}
        </div>
      </div>
      <template v-if="tabIndex === 1">
        <div class="balance">{{ $t('balance') }}: 50.234190</div>
        <div class="input-wrap">
          <input type="text" :placeholder="$t('placeholder')" v-model="count" />
          <span>TRX</span>
        </div>
      </template>
    </div>
    <div class="submit" @click="onSubmit">{{ $t('submit') }}</div>
  </div>
</template>

<script>
import BlockContent from '../components/BlockContent.vue';
export default {
  name: 'Home',
  components: { BlockContent },
  data() {
    return {
      tabIndex: 0,
      btnIndex: 0,
      count: undefined,
    };
  },
  methods: {
    onTab(index) {
      this.tabIndex = index;
    },
    onBtn(index) {
      this.btnIndex = index;
    },
    onSubmit() {
      console.log('submit');
    },
  },
};
</script>

<style lang="scss" scoped>
@mixin placeholder {
  font-size: 0.26rem;
  font-family: PingFang SC, PingFang SC-Regular;
  font-weight: 400;
  color: #9ea0a5;
}
.home {
  background: #f2f3f7;
  padding: 0.48rem 0.32rem;
  min-height: 100vh;
  .tab-wrap {
    width: 80%;
    margin: 0 auto;
    margin-top: 0.72rem;
    background: #e9ecf3;
    border-radius: 0.22rem;
    padding: 0.08rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .tab {
      flex: 1;
      text-align: center;
      font-size: 0.24rem;
      font-family: PingFang SC, PingFang SC-Medium;
      font-weight: 500;
      color: #3a3b3d;
      height: 0.64rem;
      line-height: 0.64rem;
      &.active {
        border-radius: 0.18rem;
        box-shadow: 0px 5.49px 1.83px 0px rgba(94, 136, 174, 0.04),
          0px 5.49px 14.65px 0px rgba(69, 116, 170, 0.12);
        background: #ffffff;
      }
    }
    .tab-2 {
      margin-left: 0.1rem;
    }
  }
  .freeze-content {
    margin-top: 0.32rem;
    background: #ffffff;
    border-radius: 0.24rem;
    padding: 0.43rem 0.24rem;
    .select-title {
      display: flex;
      align-items: center;
      span {
        font-size: 0.26rem;
        font-family: PingFang SC, PingFang SC-Semibold;
        font-weight: 600;
        color: #3a3b3d;
      }
      :nth-child(2) {
        margin-left: 0.16rem;
        font-size: 0.24rem;
        font-family: PingFang SC, PingFang SC-Regular;
        font-weight: 400;
        color: #9ea0a5;
      }
    }
    .select-button {
      margin-top: 0.27rem;
      display: flex;
      .button {
        width: fit-content;
        padding: 0 0.32rem;
        height: 0.5rem;
        line-height: 0.5rem;
        border: 0.02rem solid #e6e8ea;
        border-radius: 0.12rem;
        font-size: 0.24rem;
        font-family: PingFang SC, PingFang SC-Semibold;
        color: #9ea0a5;
        &.active {
          background: #ebf4ff;
          color: #2980fe;
          border: 0.02rem solid #ebf4ff;
        }
      }
      .button-2 {
        margin-left: 0.32rem;
      }
    }
    .balance {
      margin-top: 0.48rem;
      font-size: 0.26rem;
      font-family: PingFang SC, PingFang SC-Semibold;
      color: #3a3b3d;
    }
    .input-wrap {
      padding: 0.3rem 0.32rem;
      background: #f2f4f7;
      border-radius: 0.22rem;
      margin-top: 0.16rem;
      display: flex;
      align-items: center;
      input {
        background: #f2f4f7;
        font-size: 0.26rem;
        flex: 1;
        outline: none;
        border: none;
      }
      input::-webkit-input-placeholder {
        /* 使用webkit内核的浏览器 */
        @include placeholder;
      }
      input:-moz-placeholder {
        /* Firefox版本4-18 */
        @include placeholder;
      }
      input::-moz-placeholder {
        /* Firefox版本19+ */
        @include placeholder;
      }
      input:-ms-input-placeholder {
        /* IE浏览器 */
        @include placeholder;
      }

      span {
        font-size: 0.26rem;
        font-family: PingFang SC, PingFang SC-Medium;
        color: #3a3b3d;
      }
    }
  }
  .submit {
    margin-top: 0.64rem;
    background: #2980fe;
    border-radius: 0.24rem;
    padding: 0.27rem 0;
    font-size: 0.3rem;
    font-family: PingFang SC, PingFang SC-Medium;
    font-weight: 500;
    text-align: center;
    color: #ffffff;
  }
}
</style>
