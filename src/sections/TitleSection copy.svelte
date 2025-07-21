<script>
    import Window from "../lib/Window.svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    import { fade, fly } from "svelte/transition";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";
    import ObservedDiv from "../lib/ObservedDiv.svelte";

    const title = "Stand Clear of the Closing Gap";
    const subtitle =
        "how physical + digital connection have reshaped the road to employment";

    let windowIsVisible = $state(true);

    const options = {
        threshold: [0.85, 0.95],
    };

    const simpleCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const showWindowCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                windowIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const removeWindowCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                windowIsVisible = false;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<div class="car-window">
    <div class="window-container">
        {#if windowIsVisible}
            <div in:fly={{ y: 200, duration: 500 }} out:fade>
                <Window {title} {subtitle} caption="" scroll=2/>
            </div>
        {/if}
    </div>
    <ObservedDiv callback={showWindowCallback} {options}>
        <div class="dashboard"></div>
        <div class="steering-wheel"></div>
    </ObservedDiv>
</div>
<div class="left-pane"></div>
<div>

    <Scroller layout="stacked">
        {#snippet sticky()}
           
            <div>
                <p>
                    You can use Svelte to add and remove data from a Highcharts
                    chart.
                </p>
                <p>
                    When you click the button above, a third group is toggled in
                    the chart. Check out the source code to see how it's done.
                </p>
                <p>
                    <strong
                        >🤔 How might you use other HTML elements, like
                        checkboxes or radio buttons, in a similar way to filter
                        data?</strong
                    >
                </p>
            </div>
        {/snippet}

        {#snippet scrolly()}
                <ObservedDiv callback={removeWindowCallback} {options}>
        <div></div>
    </ObservedDiv>
    <h1>She is lovely</h1>
        {/snippet}
    </Scroller>
</div>

<style>
    .steering-wheel {
        border-style: outset;
        border-radius: 200px;
        width: 300px;
        height: 300px;
        border-width: 50px;
        border-color: white;
        background-color: #076bbf;
        position: absolute;
        z-index: 1;
        top: 550px;
        left: 200px;
        box-shadow:
            0 4px 8px 0 rgba(0, 0, 0, 0.2),
            0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }

    .car-window {
        background-color: black;
        position: relative;
    }

    .window-container {
        position: absolute;
        right: 100px;
        z-index: 2;
    }

    .dashboard {
        background-color: #3086cc;
        border-radius: 200px 300px 0 0;
        width: 100%;
        height: 300px;
        position: absolute;
        z-index: 1;
        top: 500px;
    }

    .left-pane {
        width: 700px;
        height: 390px;
        background-color: #076bbf;
        box-shadow:
            0 4px 8px 0 rgba(0, 0, 0, 0.2),
            0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }

    .left-pane {
        transform: rotate(60deg);
        transform-origin: 0 0;
    }
</style>
