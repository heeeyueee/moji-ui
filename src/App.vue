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
    const menuVisible=ref(false)
    provide("menuVisible",menuVisible)
    
  }
}
</script>
