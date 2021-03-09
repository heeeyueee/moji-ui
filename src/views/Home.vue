<!-- 组件说明 -->
<template>
  <div class="back">
    <div class="topnavAndBanner">
      <div class="pore pore-01"></div>
      <div class="pore pore-02"></div>
      <div class="pore pore-03"></div>
      <div class="pore pore-04"></div>
      <div class="pore pore-05"></div>
      <Topnav v-if="fullWidth<1200"/>
      <div class="banner">
        <h1>Moji-UI</h1>
        <h1>Design</h1>
        <h4>
A simple and easy-to-use UI framework made by moji proudly uses the Vue 3 Composition API, the source code is written in TypeScript, and the source code of each component is extremely concise.</h4>
        <p class="actions">
          <a href="https://github.com">GitHub</a>
          <router-link to="/doc">开始</router-link>
        </p>
      </div>
    </div>
    <div class="features">
      <ul>
        <li>
          <svg>
            <use xlink:href="#icon-vue"></use>
          </svg>
          <h3>基于 Vue 3</h3>
          <p>骄傲地使用了 Vue 3 Composition API</p>
        </li>
        <li>
          <svg>
            <use xlink:href="#icon-TS"></use>
          </svg>
          <h3>基于 TypeScript</h3>
          <p>源代码采用 TypeScript 书写（非严格检查）</p>
        </li>
        <li>
          <svg>
            <use xlink:href="#icon-deng"></use>
          </svg>
          <h3>代码易读</h3>
          <p>每个组件的源代码都极其简洁</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import Topnav from "../components/Topnav.vue";
export default {
  components: {
    Topnav,
  },
  data() {
    return {
       fullWidth:document.documentElement.clientWidth

    };
  },
  computed: {

  },
  methods: {},
  setup() {
    const fullWidth=document.documentElement.clientWidth
    console.log(document.documentElement);
    console.log(fullWidth<1200);
  
    return {
     fullWidth
    }
  }

};
</script>

<style lang="scss" scoped>
$green: #02bcb0;
$border-radius: 4px;
$color: #007974;
.topnavAndBanner {
  background-color: #c6f5ff;
  clip-path: ellipse(80% 60% at 50% 40%);
}
.features {
  margin: 64px auto;
  padding: 0 16px;
  @media (min-width: 800px) {
    width: 800px;
    >ul {
      >li {
        width: 50%;
      }
    }
  }
  @media (min-width: 1200px) {
    width: 1200px;
    >ul {
      >li {
        width: 33.3333%;
      }
    }
  }
  >ul {
    display: flex;
    flex-wrap: wrap;
    >li {
      margin: 16px 0;
      display: grid;
      justify-content: start;
      align-content: space-between;
      grid-template-areas:
        "icon title"
        "icon text";
      grid-template-columns: 80px auto;
      grid-template-rows: 1fr auto;
      >svg {
        grid-area: icon;
        width: 64px;
        height: 64px;
      }
      >h3 {
         color: #2da4c7;
        grid-area: title;
        font-size: 20px;
      }
      >p {
        grid-area: text;
        font-size:15px;
      }
    }
  }
}
.banner {
  color:#283e70;
  padding: 100px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
   h1{
    font-size: 40px;
    font-weight: 900;
  }
    h4{
    letter-spacing:1px;
    line-height: 18px;
    width: 600px;
    color: #4ea0b6;
  }

  
  >.actions {
    padding: 8px 0;
    a {
      margin: 0 8px;
     background: #399fb6;
      color: white;
      display: inline-block;
      padding: 8px 24px;
      border-radius: $border-radius;
      &:hover {
        text-decoration: none;
      }
    }
  }
}
@media (min-width: 1200px) {
.back{
  display: flex;
}
.topnavAndBanner {
  flex:1;
  height: 100vh;
  background-color: #c6f5ff;
  clip-path: ellipse(85% 54% at 15% 51%);
}
.pore {
	position: absolute;
	border-radius: 50%;
}

.pore-01 {
	width: 300px;
	height: 300px;
	top: 130px;
	left:-70px;
  background-color: #e5faff;
}

.pore-02 {
	width: 120px;
	height: 120px;
  top: 90px;
	bottom: 10%;
	left:  220px;	
  background-color: #dcf9ff;
}
.pore-03 {
	width: 120px;
	height: 120px;
  top: 350px;
	left:  280px;	
  background-color: #f4feff;
}
.pore-04 {
  
	width: 70px;
	height: 70px;
  top: 320px;
	left:  400px;	
  background-color: #e8fbff;
}
.pore-05 {

	width: 200px;
	height: 200px;
  top: 150px;
	left:  500px;	
  background-color: #d5f7ff;
}
.features {
  flex: 0.6;
  height: 80vh;
  margin: auto 80px;
  padding: 40px 16px;
   width: 1200px;
    >ul {
      >li {
        width: 100%;
      }
    }
  > ul {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    > li {
      margin: 50px 0;
      display: grid;
      justify-content: start;
      align-content: space-between;
      grid-template-areas:
        "icon title"
        "icon text";
      grid-template-columns: 80px auto;
      grid-template-rows: 1fr auto;
      > svg {
        grid-area: icon;
        width: 64px;
        height: 64px;
      }
      > h3 {
        color: #2da4c7;
        grid-area: title;
        font-size: 24px;
      }
      > p {
        grid-area: text;
        font-size:18px;
      }
    }
  }
}
.banner {
  position: relative;
  color:#283e70;
  padding: 160px 0px 0px 0px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  h1{
    font-size: 60px;
    font-weight: 900;
    margin-left: -320px ;
  }
  h4{
    letter-spacing:1px;
    line-height: 18px;
    width: 300px;
    margin-left: -230px ;
    margin-top:150px;
    color: #4ea0b6;
  }
  > .actions {
    margin-left: -310px;
    padding: 15px 0;
    a {
      letter-spacing:3px;
      margin: 0px 10px 0px 8px;
      background: #399fb6;
      color: white;
      display: inline-block;
      padding: 8px 24px;
      border-radius: 18px;
      &:hover {
        text-decoration: none;
      }
    }
  }
}


}
@media (max-width: 600px) {
   h4{
    visibility: hidden;
  }
}






</style>
