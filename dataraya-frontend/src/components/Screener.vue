<template>
    <v-container fluid>
        <h2>Screener</h2>
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
    name: 'Screener',
    mounted() {
        const script = document.createElement('script');
        script.type = 'text/javascript';
        script.src = 'https://s3.tradingview.com/external-embedding/embed-widget-screener.js';
        script.async = true;
        script.innerHTML = JSON.stringify({
            width: '100%',
            height: 550,
            defaultColumn: 'overview',
            defaultScreen: 'general',
            market: 'forex',
            showToolbar: true,
            colorTheme: 'dark',
            locale: 'en'
        });
        this.$el.querySelector('.tradingview-widget-container').appendChild(script);
    }
}
</script>

<style scoped>
.tradingview-widget-container {
    width: 100%;
    height: 550px;
}
</style>