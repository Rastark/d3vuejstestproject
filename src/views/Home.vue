<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js D3.js test App"/>
    <TestChart />
  </div>
</template>

<script>
// @ is an alias to /src
import TestChart from '@/components/TestChart.vue'
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    TestChart
  }
}
</script>
