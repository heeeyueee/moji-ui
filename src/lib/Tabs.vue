<!-- 组件说明 -->
<template>
  <div class="moji-tabs">
    <div class="moji-tabs-nav" ref="container">
      <div
        :class="{ selected: t === selected }"
        class="moji-tabs-nav-item"
        v-for="(t, index) in titles"
        :key="index"
        :ref="
          (el) => {
            if (t === selected) selectedItem = el;
          }
        "
        @click="select(t)"
      >
        {{ t }}
      </div>
      <div class="moji-tabs-nav-indicator" ref="indicator"></div>
    </div>
    <div class="moji-tabs-content">
      <!-- <component class="moji-tabs-content-item" v-for="(c,index) in defaults" :is="c" :key="index" /> -->
      <component class="moji-tabs-content-item" :is="current" :key="selected" />
    </div>
  </div>
</template>

<script lang="ts">
import { computed, onMounted, ref, onUpdated, watchEffect } from "vue";
import Tab from "../lib/Tab.vue";
export default {
  props: {
    selected: {
      type: String,
    },
  },
  components: {},
  setup(props, context) {
    const defaults = context.slots.default();
    const selectedItem = ref<HTMLDivElement>(null);
    const indicator = ref<HTMLDivElement>(null);
    const container = ref<HTMLDivElement>(null);
    onMounted(() => {
      watchEffect(() => {
        const { width } = selectedItem.value.getBoundingClientRect();
        indicator.value.style.width = width + "px";
        const { left: left1 } = selectedItem.value.getBoundingClientRect();
        const { left: left2 } = container.value.getBoundingClientRect();
        const left = left1 - left2;
        indicator.value.style.left = left + "px";
      });
    });
    //onMounted(tabMove)//第一次渲染
    //onUpdated(tabMove)//后面的更新渲染
    //watchEffect(tabMove)   会在Mounted和Updated之后都执行
    defaults.forEach((component) => {
      if (component.type !== Tab) {
        throw new Error("子标签错误");
      }
    });
    const titles = defaults.map((component) => {
      return component.props.title;
    });
    const current = computed(() => {
      return defaults.filter((component) => {
        return component.props.title === props.selected;
      })[0];
    });
    const select = (title: string) => {
      context.emit("update:selected", title);
    };
    return {
      defaults,
      titles,
      current,
      select,
      container,
      indicator,
      selectedItem,
    };
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss">
$blue: #40a9ff;
$color: #333;
$border-color: #d9d9d9;
.moji-tabs {
  &-nav {
    display: flex;
    color: $color;
    border-bottom: 1px solid $border-color;
    position: relative;
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
    &-indicator {
      position: absolute;
      height: 3px;
      background: $blue;
      left: 0;
      bottom: -1px;
      transition: all 250ms;
    }
  }
  &-content {
    padding: 8px 0;
  }
}
</style>
