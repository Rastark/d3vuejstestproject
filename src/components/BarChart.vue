<template>
  <div>
    <h1>Bar Chart using D3.js</h1>
    <svg class="bar-chart"></svg> 
  </div>
</template>

<script>
import * as d3 from 'd3';
  
export default {
  name: "BarChart",
  props: ["barChartData"],
  data() {
    return { 
      dataset: [180, 100, 56, 120, 180, 30, 40, 120, 160],
      svgWidth: 500, 
      svgHeight: 300, 
      barPadding: 5
    }
  },
  computed: {
    barData() {
      const svg = d3.select('svg')
        .attr("width", this.svgWidth)
        .attr("height", this.svgHeight)
      const barWidth = (this.svgWidth / this.dataset.length)
      return svg.selectAll("rect")
        .data(this.dataset)
        .enter()
        .append("rect")
        .attr("y", d => this.svgHeight - d)
        .attr("height", d => d)
        .attr("width", barWidth - this.barPadding)
        .attr("transform", function (d, i) {
        var translate = [barWidth * i, 0];
        return "translate("+ translate +")"
        })
  }
}
}

</script>

<style scoped>

</style>