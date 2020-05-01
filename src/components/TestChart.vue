<template>
  <div id="example">
    <svg id="svg-testChartTemp">
      <g>
      <circle r="20"
        v-for="(item, index) in dataset"
        :cx="item[0]"
        :cy="item[1]"
        :key="index"
        fill="#000"
        @click="onClick(item)" />
    </g>
    </svg>
  </div>
</template>

<script>
import dataset from './dataset.json'

Vue.component('svg-testChart', {
  template: '#svg-testChartTemp'
})

var vm = new Vue({
  el:'#example',
  data: {
    data: dataset
  },
  methods: {
    onClick(item) {
      console.log('this is the item!', item)
    }
  }
})
</script>
