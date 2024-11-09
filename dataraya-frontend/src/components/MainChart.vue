<!-- src/components/TradingViewWidget.vue -->

<template>
    <v-container style="height: 100%; width: 100%">
        <v-row>
            <v-col>
                <div class="tradingview-widget-container" style="height: 100%; width: 100%">
                    <div class="tradingview-widget-container__widget" style="height: calc(100% - 32px); width: 100%">
                    </div>
                    <div class="tradingview-widget-copyright">
                        <a href="https://www.tradingview.com/" rel="noopener nofollow" target="_blank">
                            <span class="blue-text">Track all markets on TradingView</span>
                        </a>
                    </div>
                </div>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: 'MainChart',
    mounted() {
        const script = document.createElement('script');
        script.type = 'text/javascript';
        script.async = true;
        script.src = 'https://s3.tradingview.com/external-embedding/embed-widget-advanced-chart.js';
        script.innerHTML = JSON.stringify({
            autosize: true,
            symbol: 'NASDAQ:AAPL',
            interval: 'D',
            timezone: 'Etc/UTC',
            theme: 'dark',
            style: '1',
            locale: 'en',
            allow_symbol_change: true,
            calendar: false,
            support_host: 'https://www.tradingview.com',
        });
        this.$el.querySelector('.tradingview-widget-container').appendChild(script);
    },
};
</script>

<style scoped>
.blue-text {
    color: #2196F3;
}
</style>