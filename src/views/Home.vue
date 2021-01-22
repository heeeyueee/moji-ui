<!-- 组件说明 -->
<template>
    <div class=''>
        <Topnav/>
        <div class="banner">
            <h1>moji-ui</h1>
            <h2>一个UI框架</h2>
            <p class="actions">
                <a>github</a>
                <a>开始</a>
            </p>

        </div>
    </div>
</template>

<script lang="ts">
    import Topnav from '../components/Topnav.vue'
    export default {
        components: {
            Topnav

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


</style>