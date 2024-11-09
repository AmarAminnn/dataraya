<template>
  <v-card outlined class="tradingview-widget-container">
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
          { proName: "FOREXCOM:SPXUSD", title: "S&P 500 Index" },
          { description: "", proName: "AMEX:SPY" },
          { description: "", proName: "CME_MINI:ES1!" },
          { description: "", proName: "CME_MINI:MES1!" },
          { description: "", proName: "VANTAGE:SP500" },
          { description: "", proName: "AMEX:VOO" },
          { description: "", proName: "FRED:SP500" },
          { description: "", proName: "INDEX:S5FI" },
          { description: "", proName: "INDEX:S5TH" },
          { description: "", proName: "AMEX:RSP" },
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
