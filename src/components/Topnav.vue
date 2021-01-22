<!-- 组件说明 -->
<template>
    <div class=''>
           <div class="topnav">
            <div class="logo" @click="toggleMenu">LOGO</div>
        <ul class="menu">
            <li>菜单1</li>
            <li>菜单2</li>
        </ul>
        </div>
    </div>
</template>

<script lang='ts'>
import { inject, Ref } from 'vue';
    export default {
        setup(){
            const menuVisible=inject<Ref<boolean>>('menuVisible')
            console.log(`Topnav获取到的menuvisble:${menuVisible.value}`);
            const toggleMenu=()=>{
                console.log('点击了');
                menuVisible.value = !menuVisible.value
                console.log(menuVisible.value);
            }
            return {toggleMenu}
        },
        components: {

        },
        data () {
            return {

            };
        },
        computed: {

        },
        methods: {

        },
    }
</script>

<style lang='scss' scoped>
//@import url()
.topnav {
  background: pink;
  display: flex;
  padding: 16px;
  position: relative;
  z-index: 10;
  > .logo {
    max-width: 6em;
    margin-right: auto;
  }
  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;
    > li {
      margin: 0 1em;
    }
  }
}
</style>