<template>
  <div class="main">
<!--    <top-nav @press_down="showMenu"></top-nav>-->
    <div class="_body">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import {EventBus} from '../event-bus'
import topNav from '../components/nav'
import leftMenu from '../components/modal'

export default {
  components: {
    topNav,
    leftMenu
  },
  data() {
    return {
      eventBus: EventBus,
      leftMenuStatus: false
    }
  },
  provide() {},
  watch: {},
  methods: {
    showMenu (obj) {

      this.leftMenuStatus = obj
    }
  },
  created() {},
  mounted() {},
  computed: {},
}
</script>
<style lang="less">
  .modal-left {
    position: absolute;
    top: 54px; left: 0;
    width: 100%;
    height: calc(100% - 54px);
    background-color: rgba(0, 0, 0, .5);

    /*opacity: 0;*/
    transition: all .25s;
  }
</style>
