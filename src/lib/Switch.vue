<!-- 组件说明 -->
<template>
    <div class=''>
        <button class="moji-switch" :class="{'moji-checked':value}" @click="toggle"><span></span></button>
    </div>
</template>

<script lang="ts">
import { ref } from 'vue';
    export default {
        props:{
            value:Boolean,
        },
        setup(props,context){
            const toggle=()=>{
                context.emit("update:value",!props.value)
            }
            return {toggle}
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

<style lang='scss'>
//@import url()
@mixin borderTest{
    border:1px red solid;
}
$h:22px;
$h2:$h - 4px;
.moji-switch{
    border:none;
    height: $h;
    width:$h*2;
    border-radius: $h/2;
    background-color: gray;
    position: relative;
    > span{
    position: absolute;
    top:2px;
    left: 2px;
    height: $h2;
    width: $h2;
    border-radius: $h2/2;
    background-color: white;
    transition: all 250ms;
}
&.moji-checked{
    background: #1890ff;

}
&.moji-checked >span{
    left:calc(100% - #{$h2} - 2px);
}
&:focus{
    outline: none;
}
&:active{
    > span {width: $h2 + 4px;}
  }
&.moji-checked:active{
    > span {width: $h2 + 4px; margin-left: -4px;}
  }
}




</style>