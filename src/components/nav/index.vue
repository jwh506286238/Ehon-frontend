<template>
  <div class="warp">
    <div class="nav-bar">
      <div class="left">
        <i class="menu-icon el-icon-menu" @click=""></i>
        <img class="logo" src="" alt="Logo">
      </div>

      <div class="connect">
<!--        <ul class="menu">-->
<!--          <li>Home</li>-->
<!--          <li>Auction</li>-->
<!--          <li>About</li>-->
<!--        </ul>-->
        <div v-if="!isConnected" class="connect-btn" @click="getAccount">Connect Wallet</div>
        <div v-if="isConnected" class="connect-btn hover">
            {{address.substr(0, 6) + '...' + address.substr(-4)}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import util from "@/util";
export default {
  components: {},
  data() {
      return {
          address: '',
          web3:  null,
          provider: null,
          isConnected: false,

          menu_switch: false
      }
  },
  methods: {

  },
  created() {},
  mounted() {},
  watch: {},
  computed: {},
}
</script>
<style lang="less" scoped>
  @import '../../assets/style.less';
  .warp {
    box-shadow: 0 0 10px 10px rgba(100, 100, 100, 0.1);
    background: #fff;
  }
  .nav-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: @w-100;
    height: 54px;
    top: -55px;
    padding: 0 0 0 10px;
    z-index: 3;
    -webkit-transition: top .2s ease-in-out;
    -o-transition: top .2s ease-in-out;
    transition: top .2s ease-in-out;

    .left {
      display: flex;
      align-items: center;

      .menu-icon {
        margin-right: 10px;
        transition: all .2s;
        transform: rotate(0deg);}
      .menu-icon:hover {
        transform: rotate(-90deg);}
    }

    .logo {
      border: 0;
      width: 72px;
      height: 32px;
      background-color: #0faadd;
      border: none;
    }

    .connect {
      display: flex;
      align-items: center;
    }

    .menu {
      padding: 0 20px;
      overflow: hidden;

      li {
        padding: 0 10px;
        float: left;
        cursor: pointer;

      }
    }
    .connect-btn {
      position: relative;
      top: 0; right: 10px;
      width: auto;
      height: 44px;
      line-height: 44px;
      padding: 0 20px;
      background-color: #000;
      border-radius: 20px;
      text-align: center;
      cursor: pointer;
      color: #fff;

      transition: all .2s;
    }

    .connect-btn.hover {
      height: 100%;
      right: 0;
      line-height: 55px;
      border-radius: 0;
    }

    .connect-btn:hover {
      height: 100%;
      right: 0;
      line-height: 55px;
      border-radius: 0;
    }

    @media screen and (max-width: @mobileWidth) {

    }
    @media screen and (min-width: @desktopWidth) {
      width: @w-1080px;
      margin: 0 auto;
    }
  }
</style>
