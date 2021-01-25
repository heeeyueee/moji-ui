<!-- 组件说明 -->
<template>
    <div class=''>
      <Switch v-model:value="bool"/>
    </div>
</template>

<script>
import { ref } from 'vue';
    import Switch from '../lib/Switch.vue'
    export default {
        components: {
            Switch
        },
        setup(){
            const bool=ref(false)
            return {bool}

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

</style>