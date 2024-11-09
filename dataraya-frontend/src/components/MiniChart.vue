<template>
    <v-container fluid>
        <v-row justify="center">
            <v-col cols="12" class="text-center">
                <h2>Mini Chart</h2>
            </v-col>
        </v-row>
        <div class="tradingview-widget-container">
            <div class="tradingview-widget-container__widget"></div>
            <div class="tradingview-widget-copyright">
                <a href="https://www.tradingview.com/" rel="noopener nofollow" target="_blank">
                    <span class="blue-text"></span>
                </a>
            </div>
        </div>
    </v-container>
</template>

<script>
export default {
    name: 'MiniChart',
    mounted() {
        const script = document.createElement('script');
        script.type = 'text/javascript';
        script.src = 'https://s3.tradingview.com/external-embedding/embed-widget-mini-symbol-overview.js';
        script.async = true;
        script.innerHTML = JSON.stringify({
            symbol: 'FX:EURUSD',
            width: 350,
            height: 220,
            locale: 'en',
            dateRange: '12M',
            colorTheme: 'dark',
            isTransparent: false,
            autosize: false,
            largeChartUrl: ''
        });
        this.$el.querySelector('.tradingview-widget-container').appendChild(script);
    }
}
</script>

<style scoped>
.tradingview-widget-container {
    width: 350px;
    height: 220px;
}
</style>
