<!-- 组件说明 -->
<template>
    <div class=''>
        <button><span></span></button>
    </div>
</template>

<script>
    //import x from ''
    export default {
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
@mixin borderTest{
    border:1px red solid;
}
$h:22px;
$h2:$h - 4px;
button{
    border:none;
    height: $h;
    width:$h*2;
    border-radius: $h/2;
    background-color: blue;
    position: relative;
}
span{
    position: absolute;
    top:2px;
    left: 2px;
    height: $h2;
    width: $h2;
    border-radius: $h2/2;
    background-color: white;
}

</style>