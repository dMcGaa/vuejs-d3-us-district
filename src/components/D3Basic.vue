<template>
    <UnitedStatesDistricts class="icon" />
</template>

<script>
import * as d3 from 'd3'
import UnitedStatesDistricts from '../assets/US_Congressional_districts.svg'
export default {
  name: 'D3Basic',
  components: {
    UnitedStatesDistricts
  },
  data () {
    return {
      data: [99, 71, 78, 25, 36, 92],
      line: ''
    }
  },
  mounted () {
    this.calculatePath()
  },
  methods: {
    getScales () {
      const x = d3.scaleTime().range([0, 430])
      const y = d3.scaleLinear().range([210, 0])
      d3.axisLeft().scale(x)
      d3.axisBottom().scale(y)
      x.domain(d3.extent(this.data, (d, i) => i))
      y.domain([0, d3.max(this.data, d => d)])
      return { x, y }
    },
    calculatePath () {
      const scale = this.getScales()
      const path = d3.line()
      .x((d, i) => scale.x(i))
      .y(d => scale.y(d))
      this.line = path(this.data)
    }
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
svg {
  margin: 25px;
} 
svg path {
  fill: none;
  stroke: #76BF8A;
  stroke-width: 3px;
}

</style>
