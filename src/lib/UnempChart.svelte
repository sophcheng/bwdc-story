<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import { readable } from "svelte/store";

    let chart;
    const options = {
        chart: { type: "column", backgroundColor: "#123123", borderRadius: 50, },
        title: {
            text: "Unemployment & Frequency per 100 New Yorkers by Race (2023)",
            style: {
                fontFamily: "Monaco",
                color: "#ffffff",
                fontWeight: "bold",
                fontSize: 15,
            },
        },
        xAxis: {
            categories: ["Asian", "Black", "Hispanic", "White"],
            labels: {
                style: {
                    fontFamily: "Monaco",
                    color: "#ffffff",
                    fontWeight: "bold",
                    fontSize: 15,
                },
            },
        },
        yAxis: {
            title: {
                text: "Number of Persons",
                style: {
                    fontFamily: "Monaco",
                    color: "#ffffff",
                    fontWeight: "bold",
                    fontSize: 15,
                },
            },
        },

        series: [
            {
                name: "Unemployed",
                data: [1.865, 4.066, 2.873, 2.187],
                color: "#dc5a50",
            },

            {
                name: "Total # of Tens (per 100 NYers)",
                data: [1.45, 2.08, 1.43, 3.13],
                color: "#bc1915",
            },
        ],
        // plotOptions: {
        //     series: {
        //         grouping: false
        //         },
        //     }
        legend: {
            itemStyle: {
                color: "#ffffff",
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
        width: 550px;
    }
</style>
