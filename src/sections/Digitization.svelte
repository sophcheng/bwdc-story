<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    let scroll;
</script>

<svelte:window bind:scrollY={scroll} />

<div class="">
    <Scroller layout="right">
        {#snippet sticky()}
            <h1>TRAFFIC LIGHT</h1>

            <h1>RED HAND</h1>

            <h1>BAR CHART INTO FINGERS</h1>
            <h1>CHART INTO SKYLINE</h1>
            <!-- INCLUDE CONTEXT ON NYC'S DIVERSITY, ROBUST PUBLIC TRANSIT, OVERALL PHYSICAL CONNECTIVITY -->
            <h1>SEGUE INTO INTERNET ACCESS, SUBWAY VIEW</h1>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                A wise man (my English teacher) once said that emotion is
                derived from an inability to act. Year by year, this gap between
                thought and action grows dangerously thin, thanks to technology.
            </ArticleText>
            <ArticleText>
                5 years ago, the COVID pandemic ignited an unprecedented push
                towards a digital society. But what does "digital" mean, anyway?
            </ArticleText>
            <ArticleText>
                "Digit" has Latin roots, meaning "of the toe" or "of the
                finger". However, "digital" as used with electronics refers to a
                number system (ex. binary). This duality in "digital" -- of the
                physical and of numbers -- fuzzily mirrors our current world.
                ~13% of employed New Yorkers work remotely!
            </ArticleText>
            <ArticleText>
                The weight of the journey on labors' fruits: Here are travel
                times and modes across NYC's 5 boroughs.
            </ArticleText>
            <ArticleText>
                Compare to the internet access. Discuss increasing technologization, resume bias. Importance of 
                diversity in workforce, especially WRT tech. A wise man (my English teacher) once spoke of Frankenstein:
                a creation can never be greater than its creator. Tech/AI learns from our actions, and captures the ugly truth
                of conscious and unconscious biases/prejudices (ex. resume filter bias) and makes it accessible. All 
                walks of work become increasingly digitized -- we have a duty to cultivate an inclusive, representative 
                digital world to live in parallel with our physical. (And we do see an upward trend in employment across racial demographics
                -- growing accessibility (via digital world), growing representation, steady progress)
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    h1 {
        font-size: 5rem;
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
</style>
