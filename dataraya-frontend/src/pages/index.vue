<template>
  <v-container>
    <TickerTape />
    <!-- <v-row>
      <v-col cols="8">
        <MainChart />
      </v-col>git p
      <v-col cols="4">
        <MiniChart />
      </v-col>
    </v-row> -->
    <MainChart />
    <MiniChart />
    <Screener />
    <News />
  </v-container>
</template>

<script>
import MainChart from '../components/MainChart.vue'
import MiniChart from '../components/MiniChart.vue'
import TickerTape from '../components/TickerTape.vue'
import Screener from '../components/Screener.vue'
import News from '../components/News.vue'
export default {
  components: {
    MainChart,
    MiniChart,
    TickerTape,
    Screener,
    News,
  }
}
</script>
