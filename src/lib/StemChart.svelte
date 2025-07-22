<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";

    let chart;
    const options = {
        chart: {
            type: "column",
            backgroundColor: "",
            plotBackgroundImage: "cityViewBars.png",
            borderRadius: 50,
        },
        title: {
            text: "STEM Employment Among Young STEM Graduates Nationwide (2021)",
            style: {
                fontFamily: "Arial",
                color: "navy",
                fontWeight: "bold",
                textTransform: "uppercase",
                fontSize: 15,
            },
        },
        xAxis: {
            categories: ["Asian", "Black", "Hispanic", "White"],
            labels: {
                style: {
                    fontFamily:
                        "system-ui, Avenir, Helvetica, Arial, sans-serifo",
                    color: "navy",
                    fontWeight: "bold",
                    fontSize: 15,
                },
            },
        },
        yAxis: {
            title: {
                text: "% of Respective Demographic (Sex & Race)",
                style: {
                    fontFamily: "Monaco",
                    color: "navy",
                    fontWeight: "bold",
                    fontSize: 15,
                },
            },
        },

        series: [
            {
                name: "Male STEM Employment",
                data: [62.8, 41.5, 46.4, 51.2],
                color: "#d87263",
            },
            {
                name: "Female STEM Employment",
                data: [48.2, 20.7, 26.4, 28.8],
                color: "",
            },
        ],
        plotOptions: {
            series: {
                grouping: false,
            },
        },
        legend: {
            itemStyle: {
                color: "navy",
                fontWeight: "bold",
                fontFamily: "Monaco",
                fontSize: "14px",
            },
        },
    };
</script>

<!-- <div class="chart" use:Highcharts={chartOptions}></div> -->
<div class="chart">
    <Chart bind:chart {options} highcharts={Highcharts} />
</div>

<style>
    .chart {
        -webkit-box-reflect: below -200px linear-gradient(transparent, rgba(255, 255, 255, 0.3));
    }
</style>
