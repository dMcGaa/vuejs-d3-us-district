<template>
  <div class="map" v-on:click="clickHandler">
    <UnitedStatesDistricts class="icon" />
  </div>
</template>

<script>
// import * as d3 from 'd3'
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
