<template>
    <v-container fluid>
        <v-row justify="center">
            <v-col cols="12" class="text-center">
                <h2>News</h2>
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
    name: 'News',
    mounted() {
        const script = document.createElement('script');
        script.type = 'text/javascript';
        script.src = 'https://s3.tradingview.com/external-embedding/embed-widget-timeline.js';
        script.async = true;
        script.innerHTML = JSON.stringify({
            feedMode: 'all_symbols',
            isTransparent: false,
            displayMode: 'regular',
            width: 400,
            height: 550,
            colorTheme: 'dark',
            locale: 'en'
        });
        this.$el.querySelector('.tradingview-widget-container').appendChild(script);
    }
}
</script>

<style scoped>
.tradingview-widget-container {
    width: 400px;
    height: 550px;
}
</style>