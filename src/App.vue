<template>
<div id = "App"> 
<quick-menu :menu-count=count :icon-class=icons :menu-url-list=list :position=position :backgroundColor=backgroundColor>
</quick-menu>
<table class="tg">
  <tr>
    <td class="tg-0lax" colspan="5" style="background-color:red; height:5ch">
    <font-awesome-icon icon="coffee" />
    header
    </td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2" style="background-color:blue">left</td>
    <td class="tg-0lax" colspan="3">
    <trend
      :data="[0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0, 0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0]"
      :gradient="['purple', 'purple', 'purple']"
      auto-draw
      smooth>
      </trend>
    </td>
    <td class="tg-0lax" rowspan="2" style="background-color:blue">right</td>
  </tr>
  <tr>
    <td class="tg-0lax">
    <vue-circle
        :progress="50"
        :size="200"
        :reverse="false"
        line-cap="flat"
        :fill="fill1"
        empty-fill="rgba(0, 0, 0, .1)"
        :animation-start-value="0.0"
        :start-angle="4.7"
        insert-mode="append"
        :thickness="5"
        :show-percent="false"
        @vue-circle-progress="0"
        @vue-circle-end="100">
      </vue-circle>
    </td>
    <td class="tg-0lax">
    <vue-circle
        :progress="50"
        :size="200"
        :reverse="false"
        line-cap="flat"
        :fill="fill2"
        empty-fill="rgba(0, 0, 0, .1)"
        :animation-start-value="0.0"
        :start-angle="4.7"
        insert-mode="append"
        :thickness="5"
        :show-percent="false"
        @vue-circle-progress="0"
        @vue-circle-end="100">
      </vue-circle>
    </td>
    <td class="tg-0lax">
    <vue-circle
        :progress="50"
        :size="200"
        :reverse="false"
        line-cap="flat"
        :fill="fill3"
        empty-fill="rgba(0, 0, 0, .1)"
        :animation-start-value="0.0"
        :start-angle="4.7"
        insert-mode="append"
        :thickness="5"
        :show-percent="false"
        @vue-circle-progress="0"
        @vue-circle-end="100">
      </vue-circle>
    </td>
  <tr>
    <td class="tg-0lax" colspan="5" style="background-color:red">bottom</td>
  </tr>
</table>
</div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import quickMenu from 'vue-quick-menu'
import Vue from 'vue';
import Trend from 'vuetrend';
import VueCircle from 'vue2-circle-progress'

Vue.use(Trend);

export default {
  data() { 
    return { 
      count: 4, 
      icons: ["", "", "", ""],
      list: [ { isLink: false }, { isLink: false}, { isLink: false }, { isLink: false } ],
      backgroundColor: "#1976d2",
      position: "bottom-right",
      fill1 : { gradient: ["orange", "orange", "orange"]},
      fill2 : { gradient: ["red", "red", "red"]},
      fill3 : { gradient: ["blue", "blue", "blue"]} };
      },
  name: "App",
  components: {
    HelloWorld,
    quickMenu,
    VueCircle
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  .tg  {border-collapse:collapse;border-spacing:0;}
  .tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
  .tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
  .tg .tg-0lax{text-align:center;vertical-align:top; float: center;}
  .vue-circle{float:center;}
}
</style>
