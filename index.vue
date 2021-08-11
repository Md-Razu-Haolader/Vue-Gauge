<!-- https://github.com/recogizer/gauge-chart
https://recogizer.github.io/gauge-chart/docs/
 -->
<template>
    <div :id="this.gaugeId" class="vue-gauge-item"></div>
</template>
<script>

let GaugeChart = require('./assets/bundle.js');

export default {
    name: 'vue-gauge',
    props:['refid','options'],
    mounted() {
        this.initPlugin(this.options);
    },
    methods: {
        initPlugin(options = {}){
            if(this.gaugeId){
                let config = {
                    hasNeedle: true,
                    needleColor: '#f76c57',
                    needleUpdateSpeed: 1000,
                    arcColors: ['#85a3ca', '#d3d3d3'],
                    arcDelimiters: [70],
                    rangeLabel: ['0', '100'],
                    chartWidth: 250,
                    needleValue: 70
                };
                config = { ...config, ...options };

                // Element inside which you want to see the chart
                let element = document.querySelector("#"+this.gaugeId );
                
                // Drawing and updating the chart
                this.gauge = GaugeChart.gaugeChart(element, config.chartWidth, config);
                this.gauge.updateNeedle(config.needleValue); 
            }  
        },
        reloadPlugin() {
            if (this.gauge) {
                this.gauge.removeGauge();
            }
            this.initPlugin(this.options);
        }
    },
    computed: {
        gaugeId(){
            if(typeof this.refid != 'undefined'){
                return this.refid;
            }
            return "vue-gauge";
        }
    },
    watch: {
        options: function(newOptions, oldOptions) {
            // Reload gauge on nedleValue change
            if (newOptions.needleValue != oldOptions.needleValue) {
                this.reloadPlugin();
            }
        }
    }
}
</script>