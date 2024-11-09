<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <TickerTape />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <MainChart />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="4" style="padding: 20px;">
        <Screener />
      </v-col>
      <v-col cols="4">
        <MiniChart />
      </v-col>
      <v-col cols="4">
        <News />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <TableuEmbed />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import MainChart from '../components/MainChart.vue'
import MiniChart from '../components/MiniChart.vue'
import TickerTape from '../components/TickerTape.vue'
import Screener from '../components/Screener.vue'
import News from '../components/News.vue'
import TableuEmbed from '../components/TableuEmbed.vue'

export default {
  components: {
    MainChart,
    MiniChart,
    TickerTape,
    Screener,
    News,
    TableuEmbed
  },
  mounted() {
    document.title = 'DataRaya'
  }
}
</script>
