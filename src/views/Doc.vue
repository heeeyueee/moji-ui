<!-- 组件说明 -->
<template>
    <div class=''>
        <Topnav/>
        <div class="content">
            <aside>边栏</aside>
            <main>主内容</main>
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

<style lang="scss" scoped>


</style>