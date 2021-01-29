<!-- 组件说明 -->
<template>
    <div class=''>
        <h3>示例1</h3>
        <Tabs v-model:selected="selectedTitle">
            <Tab title="导航一">内容一</Tab>
            <Tab title="导航二">内容二</Tab>
        </Tabs>
    </div>
</template>

<script lang="ts">
import { ref } from 'vue'
    import Tab from "../lib/Tab.vue"
    import Tabs from "../lib/Tabs.vue"
    export default {
        components: {
            Tab,
            Tabs

        },
        setup(){
            const selectedTitle=ref("导航一")
            return {selectedTitle}

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