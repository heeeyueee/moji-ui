<!-- 组件说明 -->
<template>
  <div class="">
    <div class="topnav">
      <router-link to="/" class="logo">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-huaban"></use>
        </svg>
        <p>moji-desgin</p>
      </router-link>
      <ul class="menu">
        <li>
          <router-link to="/doc">文档</router-link>
        </li>
      </ul>
      <svg
        v-if="toggleMenuButtonVisible"
        class="toggleAside"
        @click="toggleMenu"
      >
        <use xlink:href="#icon-gengduo"></use>
      </svg>
    </div>
  </div>
</template>

<script lang="ts">
import { inject, Ref } from "vue";
export default {
  props: {
    toggleMenuButtonVisible: {
      type: Boolean,
      default: false,
    },
  },
  setup() {
    const menuVisible = inject<Ref<boolean>>("menuVisible");
    console.log(`Topnav获取到的menuvisble:${menuVisible.value}`);
    const toggleMenu = () => {
      console.log("点击了");
      menuVisible.value = !menuVisible.value;
      console.log(menuVisible.value);
    };
    return { toggleMenu };
  },
  components: {},
  data() {
    return {};
  },
  computed: {},
  methods: {},
};


</script>

<style lang="scss" scoped>
//@import url()
$color: #007974;
.topnav {
      border-bottom: 1px solid;
    background: #fff;
   box-shadow: 0 3px 3px #c6f5ff;
  color: $color;
  display: flex;
  padding: 16px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 20;
  > .logo {
    display: flex;
    max-width: 15em;
    margin-right: auto;
    > svg {
      width: 32px;
      height: 32px;
    }
    p{
      font-size: 18px;
      font-weight: 700;
      margin-left: 10px;
      color: #283e70;
    }
    
  }
  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;
    > li {
      margin: 0 1em;
    }
  }
  > .toggleAside {
    width: 32px;
    height: 32px;
    background: fade-out(black, 0.9);
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    display: none;
  }
  @media (max-width: 500px) {
    > .menu {
      display: none;
    }
    > .logo {
      margin: 0 auto;
    }
    > .toggleAside {
      display: inline-block;
    }
  }
}
</style>
