<template>
  <div class="container">
    <h2>
      Stationen
    </h2>

    <ul>
      <li v-for='(station, index) in stations' :key='index'>
        {{ station.properties.name }}
      </li>
    </ul>

    <div>
      Jahresmittelwert: {{ annualMeanValue }} µg/m³
    </div>
    <div>
      Heute {{ now }}:00 Uhr: {{ nowValue }} µg/m³
    </div>
  </div>
</template>

<script>
  import stations from '../data/stations.json'

  export default {
    components: {},
    data: function () {
      return {
        annualMeanValue: '31',
        nowValue: '21',
        now: undefined,
        stations: stations.features
      }
    },
    methods: {},
    mounted: function () {
      this.now = new Date().getHours()
    }
  }
</script>

<style scoped>
  .container {
    display: flex;
    flex-direction: column;
    > div {
      flex: 1;
    }
  }
</style>
