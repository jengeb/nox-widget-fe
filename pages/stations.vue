<template>
  <b-container fluid>
    <b-row align-v="center">
      <b-col cols="1" sm="1">
        <span v-if="counter !== 0">
          <a class="icon-left-open link" @click="counter--" />
        </span>
      </b-col>
      <b-col cols="11" sm="10" style="text-align:center">
        <h2>
          {{ stations[counter].properties.name }}
        </h2>
        <div style="margin-bottom: 1.5rem;">
          Jahresmittelwert: {{ annualMeanValue }} µg/m³
        </div>
        <div class="navigation">
          <span v-for="(station, index) in stations" :key="index">
            <svg height="25" width="25">
              <circle v-if="counter === index" class="link" cx="15" cy="15" r="8" fill="yellow" @click="counter = index" />
              <circle v-else class="link" cx="15" cy="15" r="8" fill="grey" @click="counter = index" />
            </svg>
          </span>
        </div>
        <div>
          Chart
        </div>
        <div>
          Heute {{ now }}:00 Uhr: {{ nowValue }} µg/m³
        </div>
      </b-col>
      <b-col cols="1" sm="1">
        <span v-if="counter < stations.length - 1">
          <a class="icon-right-open link" @click="counter++" />
        </span>
      </b-col>
    </b-row>
  </b-container>
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
        stations: stations.features,
        counter: 0
      }
    },
    methods: {},
    mounted: function () {
      this.now = new Date().getHours()
    }
  }
</script>

<style scoped>
  @import '~/assets/style/base.css'

  .container {
    display: flex;
    flex-direction: column;
    > div {
      flex: 1;
    }
  }

  .link {
    text-decoration: none;
    cursor: pointer;
    &:hover {
      fill: yellow;
    }
  }

  .navigation {
    margin-bottom: 1.5rem;
  }
</style>
