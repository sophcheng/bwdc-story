<script>
    import { fade } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import UnempChart from "../lib/UnempChart.svelte";
    let scroll;
</script>

<svelte:window bind:scrollY={scroll} />

<div class="">
    <Scroller layout="right">
        {#snippet sticky()}
            <div class="lights">
                <img
                    class="traffic-img"
                    src="emptyTrafficLight.png"
                    alt="Traffic light, resembling the three dots at upper left of a window."
                />
                <div class="dot-container">
                    {#if scroll >= 750 && scroll <= 1560}
                        <div class="reddot" in:fade out:fade></div>
                    {/if}
                    {#if scroll >= 1760 && scroll <= 2100}
                        <div class="yellowdot" in:fade out:fade></div>
                    {/if}
                    {#if scroll >= 2300}
                        <div class="greendot" in:fade out:fade></div>
                    {/if}
                </div>
            </div>
            <i><h1 class="title">DIGITIZATION</h1></i>
            <div class="hand-container">
                <img
                    class="hand-img"
                    src="stopHand.png"
                    alt="Hand resembling crosswalk stopping hand."
                    style:transform={`translate3d(${scroll >= 2720 ? 40 : 0}px, ${scroll >= 1800 ? 0 : scroll}px, ${scroll >= 3600 ? 1 : 200}px) scale(${scroll >= 3400 ? 3 : 1})
                    `}
                    style:opacity={scroll >= 3500 ? 0 : 1}
                    style:z-index={scroll >= 3500 ? -10 : 2}
                />
                <div
                    class="walkbox"
                    style:opacity={scroll >= 2730 ? 1 : 0}
                    style:transform={`translate3d(0, ${scroll >= 2730 ? 0 : scroll}px, 0)`}
                    style:transition={`1.5s`}
                >
                    <div class="chart" style:opacity={scroll >= 3500 ? 1 : 0}>
                        <UnempChart></UnempChart>
                    </div>
                </div>
            </div>

            <!-- <h1>BAR CHART INTO FINGERS</h1>
            <h1>CHART INTO SKYLINE</h1>
            INCLUDE CONTEXT ON NYC'S DIVERSITY, ROBUST PUBLIC TRANSIT, OVERALL PHYSICAL CONNECTIVITY
            <h1>SEGUE INTO INTERNET ACCESS, SUBWAY VIEW</h1> -->
        {/snippet}

        {#snippet scrolly()}
            <ArticleText color="#3086cc">
                A wise man (my English teacher) once said that emotion is
                derived from an inability to act. <strong
                    >Year by year, this gap between thought and action grows
                    thinner, thanks to technology.</strong
                >
            </ArticleText>
            <ArticleText color="#3086cc">
                5 years ago, the COVID pandemic ignited an unprecedented push
                towards a digital society. <strong
                    >But what does "digital" mean, anyway?</strong
                >
            </ArticleText>
            <ArticleText color="#3086cc">
                <strong>"Digit"</strong> has Latin roots, meaning
                <strong>"of the toe"</strong>
                or <strong>"of the finger"</strong>. It also refers to a
                <strong>number system</strong> (ex. binary). This duality in "digital"
                -- of the physical and of numbers -- fuzzily mirrors our current
                world!
            </ArticleText>
            <ArticleText color="coral">
                A wise man (my English teacher) once spoke on Frankenstein: <strong
                    >a creation can never be greater than its creator.</strong
                >
            </ArticleText>
            <ArticleText color="coral">
                Tech/AI learns from our actions, and captures the ugly truth of
                conscious and unconscious prejudices, and makes these biases,
                among a multitude of other things, accessible.
            </ArticleText>
            <ArticleText color="purple">
                All walks of work are becoming increasingly digitized -- <strong
                    style="color: purple;"
                    >we have a duty to cultivate an inclusive, representative
                    digital world to live in parallel with our physical!</strong
                >
            </ArticleText>
            <!-- Compare to the internet access. Discuss increasing
                technologization, resume bias. Importance of diversity in
                workforce, especially WRT tech. (And we do see an upward trend in employment
                across racial demographics -- growing accessibility (via digital
                world), growing representation, steady progress) -->
        {/snippet}
    </Scroller>
</div>

<style>
    h1 {
        font-size: 5rem;
        letter-spacing: 1px;
        color: #873512;
        text-shadow:
            1px 1px 0 #007052,
            2px 2px 0 #873512;
        text-transform: uppercase;
        margin-left: 2em;
    }

    p {
        font-size: 1.3rem;
        color: #873512;
        margin-top: 1rem;
        margin-left: 2em;
    }
    .title {
        position: relative;
        z-index: 0;
        top: -620px;
        left: 350px;
    }
    .hand-img {
        width: 200px;
        margin: 0px auto;
        z-index: 2;
        position: relative;
        left: 250px;
        bottom: -390px;
        transition: 0.3s;
    }
    .walkbox {
        position: relative;
        z-index: 1;
        width: 550px;
        height: 400px;
        background-color: #123123;
        border-radius: 50px;
        border-width: 15px;
        border-color: goldenrod;
        border-style: outset;
        bottom: 20px;
    }
    .hand-container {
        position: absolute;
        width: 550px;
    }

    .traffic-img {
        width: 250px;
        margin: 0px auto;
        margin-bottom: 50px;
        z-index: 2;
        position: relative;
        top: 100px;
    }
    .lights {
        position: relative;
    }
    .reddot,
    .yellowdot,
    .greendot {
        width: 90px;
        height: 90px;
        border-radius: 45px;
        position: relative;
        z-index: 0;
        left: 90px;
    }
    .dot-container {
        top: -400px;
        /* background-color: goldenrod; */
        width: 90px;
        height: 400px;
        position: relative;
    }

    .reddot {
        top: 150px;
        margin-left: 0px;
        background-color: red;
    }
    .yellowdot {
        top: 250px;
        background-color: rgb(251, 228, 112);
    }
    .greendot {
        top: 350px;
        background-color: green;
        overflow-y: hidden;
    }
    .chart {
        /* position: relative; */
    }
</style>
