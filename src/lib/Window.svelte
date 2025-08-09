<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";

    let { title, subtitle, caption, scroll, subcaption } = $props();

    let options = {
        chart: {
            backgroundColor: "#873512",
            // plotBackgroundColor: "#ffffff",
            type: "pie",
            borderRadius: 25,
        },
        title: {
            text: "Diversity of NYC Government Workers",
            verticalAlign: "bottom",
            style: {
                fontFamily: "Monaco",
                color: "#ffffff",
                fontWeight: "bold",
                fontSize: 15,
            },
        },
        plotOptions: {
            pie: {
                innerSize: "45%",
                allowPointSelect: true,
                dataLabels: [
                    {
                        enabled: true,
                        distance: 20,
                        backgroundColor: "rgba(252, 255, 197, 0.7)",
                        borderRadius: 10,
                    },
                    {
                        enabled: true,
                        distance: -40,
                        format: "{point.percentage:.1f}%",
                        style: {
                            fontSize: "1.2em",
                            textOutline: "none",
                        },
                        filter: {
                            operator: ">",
                            property: "percentage",
                            value: 10,
                        },
                    },
                ],
            },
        },
        series: {
            name: "Group",
            data: [
                {
                    name: "Asian",
                    y: 25079,
                },
                {
                    name: "Black",
                    sliced: true,
                    selected: true,
                    y: 69769,
                },
                {
                    name: "Hispanic",
                    y: 43481,
                },
                {
                    name: "White",
                    y: 56500,
                },
                {
                    name: "Other",
                    y: 3143,
                },
                {
                    name: "Prefer not say",
                    y: 20027,
                },
            ],
        },
    };
</script>

<svelte:window bind:scrollY={scroll} />

<div class="title-card">
    <div class="window-box">
        <div class="header">
            <div
                style:transform={`translate3d(${Math.min(scroll, 130)}px, 0px, 0)`}
                style:transition={"1.5s"}
            >
                <button class="reddot"></button>
                <button class="yellowdot"></button>
                <button class="greendot"></button>
            </div>
        </div>
        <div class="window-content">
            <div>
                <i><h1>{title}</h1></i>
                <p
                    style:transform={`translate3d(${Math.min(scroll, 200)}px, 0px, 0)`}
                    style:transition={"1.5s"}
                >
                    {subtitle}
                </p>
                <p>
                    {caption}
                </p>
                <i
                    ><p
                        style:transform={`translate3d(${Math.min(scroll, 180)}px, 0px, 0)`}
                        style:transition={"1.5s"}
                    >
                        ({subcaption})
                    </p></i
                >
            </div>
            <div class="chart">
                <Chart {options} highcharts={Highcharts} />
            </div>
        </div>
    </div>
</div>

<style>
    * {
        box-sizing: border-box;
    }

    .title-card {
        display: flex;
        flex-direction: row;
        height: 100vh;
        justify-content: center;
        /* align-items: center; */
        /* text-align: center; */
        padding: 2rem;
        box-sizing: border-box;
        font-family: "Monaco", monospace;
    }

    .header {
        display: flex;
        height: 70px;
        background-color: #3086cc;
        border-radius: 50px 50px 0 0;
        align-items: center;
        border-style: outset outset none none;
    }

    .window-box {
        display: flex;
        flex-direction: column;
        background-color: #f0ecd9;
        width: 900px;
        height: 600px;
        border-radius: 50px 50px 50px 50px;
        /* margin-left: auto; */
        align-self: center;
        border-style: outset;
        border-color: goldenrod;
        box-shadow:
            0 4px 8px 0 rgba(0, 0, 0, 0.2),
            0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .window-content {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .chart {
        width: 650px;
        margin: 60px 15px 15px 15px;
    }

    h1 {
        font-family: system-ui, Avenir, Helvetica, Arial, sans-serif;
        font-size: 3rem;
        color: #873512;
        text-shadow:
            1px 1px 0 #007052,
            2px 2px 0 #873512;
        text-transform: uppercase;
        margin-left: 1em;
    }

    p {
        font-size: 1.3rem;
        color: #873512;
        margin-top: 1rem;
        margin-left: 2em;
        min-height: 1em;
    }

    i p {
        opacity: 0;
        animation: delayed-entry 1s ease forwards;
        animation-delay: 1.5s;
    }

    @keyframes delayed-entry {
        0% {
            opacity: 0;
            color: red;
        }
        100% {
            opacity: 1;
            color: #3086cc;
        }
    }

    @media (max-width: 600px) {
        h1 {
            font-size: 2.2rem;
        }

        p {
            font-size: 1.1rem;
        }
    }
</style>
