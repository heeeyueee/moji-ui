<!-- 组件说明 -->
<template>
    <div class="moji-tabs">
  <div class="moji-tabs-nav">
    <div :class="{selected:t===selected}" class="moji-tabs-nav-item" 
    v-for="(t,index) in titles" :key="index"
    @click="select(t)">{{t}}</div>
  </div>
  <div class="moji-tabs-content">
    <!-- <component class="moji-tabs-content-item" v-for="(c,index) in defaults" :is="c" :key="index" /> -->
    <component class="moji-tabs-content-item" :is="current"  :key="selected">
  </div>
</div>
</template>

<script lang="ts">
import { computed } from 'vue';
    import Tab from '../lib/Tab.vue'
    export default {
        props:{
            selected:{
                type:String
            }
        },
        components: { 
        },
        setup(props,context){
                const defaults=context.slots.default()
                console.log(defaults);
                defaults.forEach((component)=>{
                    if(component.type!==Tab){
                        throw new Error("子标签错误")
                    }
                })
                const titles=defaults.map((component)=>{
                    return component.props.title
                })
                const current=computed(()=>{
                  return defaults.filter((component)=>{
                    return component.props.title===props.selected
                })[0]
                })
                const select=(title:string)=>{
                    context.emit("update:selected",title)
                }
                return {defaults,titles,current,select}   
            },
        data () {
            return {

            };
        }
    }
</script>

<style lang='scss' >
$blue: #40a9ff;
$color: #333;
$border-color: #d9d9d9;
.moji-tabs {
  &-nav {
    display: flex;
    color: $color;
    border-bottom: 1px solid $border-color;
    &-item {
      padding: 8px 0;
      margin: 0 16px;
      cursor: pointer;
      &:first-child {
        margin-left: 0;
      }
      &.selected {
        color: $blue;
      }
    }
  }
  &-content {
    padding: 8px 0;
  }
}

</style>