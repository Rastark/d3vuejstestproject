<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js D3.js test App"/>
    <BarChart />
    <BubbleChart :tweetData=loadDataBubbleChart />
  </div>
</template>

<script>
// @ is an alias to /src
import * as d3 from 'd3';

import HelloWorld from '@/components/HelloWorld.vue';
import BarChart from '@/components/BarChart.vue';
import BubbleChart from '@/components/BubbleChart.vue';

export default {
  name: 'Home',
  components: {
    HelloWorld,
    BarChart,
    BubbleChart
  },
  data() {
    return {
      loadDataBubbleChart: {}
    };
  },
  mounted() {
    console.log("App loaded");
    this.fetchData();
  },
  methods: {
    async fetchData() {
      let dataBubbleChart = await d3.json("./exampleData.json");
      this.loadDataBubbleChart = dataBubbleChart;
      let dataBarChart = await d3.json("./italyaging.json")
    }
  }
}
</script>
