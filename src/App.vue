<template>
<div id = "App"> 
<quick-menu :menu-count=count :icon-class=icons :menu-url-list=list :position=position :backgroundColor=backgroundColor>
</quick-menu>
<table class="tg">
  <tr>
    <td class="tg-0lax" colspan="5" style="height:5ch;background-color:#efefef">
    <font-awesome-icon icon="warehouse" />
    Overview
    </td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2" style="background-color:#efefef"></td>
    <td class="tg-0lax" colspan="3">
    <trend
      :data=mydata
      :gradient="['#55efc4', '#55efc4', 'purple']"
      auto-draw
      smooth>
      </trend>
    </td>
    <td class="tg-0lax" rowspan="2" style="background-color:#efefef"></td>
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
        <p>50%</p>
      </vue-circle>
    </td>
    <td class="tg-0lax">
    <vue-circle
        :progress="80"
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
        <p>80%</p>
      </vue-circle>
    </td>
    <td class="tg-0lax">
    <vue-circle
        :progress="20"
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
        <p>20%</p>
      </vue-circle>
    </td>
  <tr>
    <td class="tg-0lax" colspan="5" style="background-color:#efefef"></td>
  </tr>
</table>
</div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import quickMenu from "vue-quick-menu";
import Vue from "vue";
import Trend from "vuetrend";
import VueCircle from "vue2-circle-progress";

Vue.use(Trend);

export default {
  data() {
    return {
      count: 4,
      icons: ["", "", "", ""],
      list: [
        { isLink: false },
        { isLink: false },
        { isLink: false },
        { isLink: false }
      ],
      backgroundColor: "#1976d2",
      position: "bottom-right",
      fill1: { gradient: ["#d63031", "orange", "#e17055"] },
      fill2: { gradient: ["#e17055", "#0984e3", "#0984e3"] },
      fill3: { gradient: ["#6c5ce7", "#6c5ce7", "#6c5ce7"] },
      mydata: myFunct()
    };
  },
  name: "App",
  components: {
    HelloWorld,
    quickMenu,
    VueCircle
  }
};

function myFunct(){
  return [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0, 0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0]
};
</script>

<style>
#App {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
  color: #636e72;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: @font-size;
  background-color: #efefef;
}
.tg {
  border-collapse: separate;
  border-radius: 0px;
  border-spacing: 10px;
}
.tg td {
  padding: 10px 5px;
  border-style: solid;
  border-width: 0px;
  overflow: hidden;
  border-radius: 2px;
  word-break: normal;
}
.tg th {
  padding: 10px 5px;
  border-style: solid;
  border-width: 0px;
  overflow: hidden;
  word-break: normal;
}
.tg .tg-0lax {
  text-align: center;
  vertical-align: top;
  float: center;
  background-color: white;
}
vue-circle {
  float: center;
}
</style>
