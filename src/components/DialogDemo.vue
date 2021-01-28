<!-- 组件说明 -->
<template>
    <div class=''>
        <div>
            <h3>示例1</h3>
            <Button @click="handelToggle">toggle</Button>
            <Dialog v-model:visible="dialogVisible" :ok="handleOk" :cancel="handleCancel" :closeOnClickOverlay="false">
                <template v-slot:title>
                    <strong>标题</strong>
                </template>
                <template v-slot:content>
                    <h2>你好</h2>
                    <h3>hi</h3>
                </template>
            </Dialog>
            <h1>示例2</h1>
            <Button @click="showDialog">show</Button>
        </div>
    </div>
</template>

<script lang="ts">
    import Dialog from '../lib/Dialog.vue'
    import Button from '../lib/Button.vue'
    import { ref,h } from 'vue'
    import { openDialog } from '../lib/openDialog'
    export default {
        components: {
            Dialog,
            Button
        },
        setup(){
            const dialogVisible=ref(false)
            const handelToggle=()=>{
                dialogVisible.value=!dialogVisible.value
            }
            const handleOk=()=>{
                return true

            }
            const handleCancel=()=>{

            }
            const showDialog = () => {
            openDialog({
                title: h('strong', {}, '标题'),
                content: '你好',
                ok() {
                   console.log('ok')
                },
                cancel() {
                   console.log('cancel')
                }
             })
             }
            return {dialogVisible,handelToggle,handleOk,handleCancel,showDialog}
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