<template>
  <div class="map" v-on:click="clickHandler">
    <UnitedStatesDistricts  class="icon" />
  </div>
</template>

<script>
// <UnitedStatesDistricts  class="icon" />
import * as d3 from 'd3'
import UnitedStatesDistricts from '../assets/US_Congressional_districts.svg'
export default {
  name: 'DistrictMap',
  components: {
    UnitedStatesDistricts
  },
  data () {
    return {
    }
  },
  mounted () {
    var svg = d3.select('div.map > svg')
    .call(d3.zoom().on('zoom', function () {
      svg.attr('transform', d3.event.transform)
    }))

  /*
  var svg = d3.select('div.map')
    .append('svg')
    .attr('width', '100%')
    .attr('height', '100%')
    .call(d3.zoom().on('zoom', function () {
      svg.attr('transform', d3.event.transform)
    }))
    /*
    .append('g')

    svg.append('circle')
    .attr('cx', document.body.clientWidth / 2)
    .attr('cy', document.body.clientHeight / 2)
    .attr('r', 50)
    .style('fill', '#B8DEE6')
    */
  },
  methods: {
    clickHandler: function (event) {
      console.log('clicked', event)
    }
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.map {
  background-color: aqua;
}

svg path:hover {
  fill: orange;
  stroke: blue;
  stroke-width: 3px;
}

</style>
