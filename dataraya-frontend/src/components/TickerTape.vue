<template>
  <v-card outlined class="tradingview-widget-container">
    <h2>Ticker Tape</h2>
    <div class="tradingview-widget-container__widget"></div>
    <div class="tradingview-widget-copyright">
      <a href="https://www.tradingview.com/" rel="noopener nofollow" target="_blank">
      </a>
    </div>
  </v-card>
</template>

<script>
export default {
  name: "TickerTape",
  mounted() {
    if (!document.getElementById("tradingview-ticker-tape-script")) {
      const script = document.createElement("script");
      script.id = "tradingview-ticker-tape-script";
      script.src = "https://s3.tradingview.com/external-embedding/embed-widget-ticker-tape.js";
      script.async = true;
      script.innerHTML = JSON.stringify({
        symbols: [
          { proName: "FRED:SP500", description: "" },
          { proName: "SP:S5INFT", description: "" },
          { proName: "SP:SPF", description: "" },
          { proName: "SP:S5HLTH", description: "" },
          { proName: "SP:SPN", description: "" },
          { proName: "SP:S5REAS", description: "" },
          { proName: "SP:S5COND", description: "" },
          { proName: "SP:S5INDU", description: "" },
          { proName: "SP:S5MATR", description: "" },
          { proName: "SP:S5UTIL", description: "" },
        ],
        showSymbolLogo: true,
        isTransparent: false,
        displayMode: "adaptive",
        colorTheme: "light",
        locale: "en",
      });
      this.$el.querySelector(".tradingview-widget-container__widget").appendChild(script);
    }
  },
};
</script>

<style scoped>
.tradingview-widget-container {
  padding: 16px;
}

.blue-text {
  color: #2962ff;
}
</style>
