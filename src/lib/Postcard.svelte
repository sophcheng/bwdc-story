<script>
    import { fly, fade } from "svelte/transition";
    import StemChart from "./StemChart.svelte";
    import Scroller from "./Scroller.svelte";
    let { scroll } = $props();
</script>

<Scroller layout="stacked">
    {#snippet sticky()}
        <img
            src="postcardShot.png"
            alt="Postcard-esque drawing of a city and autumn foilage."
            class="background"
        />
    {/snippet}
    {#snippet scrolly()}
        <div class="card-container">
            {#if scroll >= 4000 && scroll <= 4915}
                <div
                    class="card-front"
                    in:fly={{ y: 200, duration: 500 }}
                    out:fade
                >
                    <div class="skyline-graph">
                        <StemChart></StemChart>
                    </div>
                    <div class="graph-analysis">
                        <h1>Greetings from a Tech Past, Present, & Future!</h1>
                        <p>
                            STEM remains key to societal innovation, across
                            data, recruiting, and even creative fields!
                            (Shoutout to STEAM!)
                        </p>
                        <p>
                            Overall, <strong
                                >31.1% of black STEM graduates work in their
                                field</strong
                            >, which is lowest compared to
                            <strong>55.5%, 36.4%,</strong>
                            and
                            <strong>40%</strong> of Asian, Hispanic, and white graduates
                            respectively.
                        </p>
                    </div>
                </div>
            {:else}
                <div
                    class="card-back"
                    in:fly={{ x: 200, duration: 500 }}
                    out:fade
                >
                    <div class="card-back-left">
                        <h2>
                            <span style="font-size:xx-large;">D</span>espite
                            having the same STEM background, this disparity in
                            post-grad outcomes nods to
                            <span style="color:#873512;"
                                >potentially flawed trends in STEM recruiting
                                and education</span
                            >:
                        </h2>
                        <h2>
                            the search processes and necessary encouragement +
                            support from academic peers.
                        </h2>
                        <div class="reaching-hands">
                            <img
                                src="stopHand.png"
                                alt="Left stoplight-esque hand reaching out to right."
                                class="decal-left"
                            />
                            <img
                                src="stopHand.png"
                                alt="Right stoplight-esque hand reaching out to left."
                                class="decal-right"
                            />
                        </div>
                        <h2>
                            Still, the means in which we reach out to one
                            another are perpetually shifting.
                        </h2>
                    </div>
                    <div class="card-back-right">
                        <div class="wave">
                            <h3>~~~~~~~~~~</h3>
                            <h3>~~~~~~~~~~</h3>
                            <h3>~~~~~~~~~</h3>
                            <!-- <div class="wavy-top"></div>
                            <div class="wavy-bottom"></div>
                            <div class="wavy-top"></div> -->
                        </div>

                        <div class="stamp">
                            <img
                                src="trafficLight.png"
                                alt="Stamp of a traffic light."
                                class="stamp-img"
                            />
                        </div>
                        <h2 class="address">
                            <span style="font-size:xx-large;">Y</span>et these
                            changes offer opportunities for equity, through the
                            <span style="color:#873512;"
                                >increasing accessibility, connectivity, and
                                consistency</span
                            >
                            we always reach out with,
                            <span style="font-size:xx-large; color:#873512;"
                                >closing the gap bit by bit.</span
                            >
                        </h2>
                    </div>
                </div>
            {/if}
        </div>
    {/snippet}
</Scroller>

<style>
    .card-container {
        position: relative;
    }
    .background {
        position: absolute;
        z-index: 0;
    }
    .card-front,
    .card-back {
        position: absolute;
        top: -500px;
        display: flex;
        justify-self: center;
        justify-content: center;
        align-items: center;

        background-color: #f0ecd9;
        width: 1000px;
        height: 700px;
        border-radius: 15px;
        border-style: dotted;
        border-width: 15px;
        border-color: white;
        padding: 10px;
        margin-bottom: 40px;
        box-shadow:
            0 4px 8px 0 rgba(0, 0, 0, 0.3),
            0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .card-front {
        flex-direction: column;
    }
    .card-back {
        flex-direction: row;
    }
    .card-back-left,
    .card-back-right {
        flex-direction: column;
        width: 50%;
        padding: 25px;
    }
    .card-back-right {
        border-style: double;
        border-width: 0 0 0 10px;
        border-color: #873512;
        position: relative;
    }
    .wave {
        position: absolute;
        left: 100px;
    }
    .stamp {
        width: 100px;
        justify-self: flex-end;
        background-color: #b8e2eb;
        border-style: dotted;
        border-width: 5px;
        border-color: white;
        padding: 5px;
        box-shadow:
            0 4px 8px 0 rgba(0, 0, 0, 0.3),
            0 6px 20px 0 rgba(0, 0, 0, 0.1);
    }
    .stamp-img {
        width: 100px;
    }
    .decal-left,
    .decal-right {
        width: 50px;
        margin: 0 20px 0 20px;
    }
    .decal-left:hover,
    .decal-right:hover {
        margin: 0;
        transition: 0.5s ease;
    }
    .decal-left {
        transform: rotate(120deg);
        opacity: 0.7;
    }
    .decal-right {
        transform: rotate(-120deg);
    }

    .reaching-hands {
        display: flex;
        flex-direction: row;
        justify-content: center;
        width: 400px;
    }

    .address {
        border-style: dashed;
        padding: 15px;
        border-radius: 15px;
        border-color: #873512;
    }
    .skyline-graph {
        width: 900px;
        height: 500px;
        margin-top: 40px;
        background-color: #b8e2eb;
        border-style: double;
        border-width: 10px;
        border-color: white;
    }
    .graph-analysis {
        font-family: "Monaco";
        color: #873512;
        align-self: flex-start;
        margin: 0 50px 0 50px;
    }
    p {
        font-family: system-ui, Avenir, Helvetica, Arial, sans-serif;
    }
    h2 {
        font-family: "Monaco";
        color: navy;
        align-self: flex-start;
    }
    h3 {
        /*For postal stamp "waves"*/
        margin: -20px 0 -20px 0;
        font-size: 50px;
        letter-spacing: -10px;
        color: #3086cc;
        text-align: right;
        transform: rotate(-2deg);
        opacity: 0.8;
    }
</style>
