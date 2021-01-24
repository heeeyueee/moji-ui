<template>
  <router-view></router-view>
</template>

<script>
import { provide, ref } from 'vue'

export default {
  name: 'App',
  components: {
   
  },
  setup(props) {
    const width = document.documentElement.clientWidth;
    const menuVisible = ref(width <= 500 ? false : true);
    provide("menuVisible",menuVisible)
    
  }
}
</script>
