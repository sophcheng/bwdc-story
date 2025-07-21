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
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                A wise man (my English teacher) once said that emotion is
                derived from an inability to act.
            </ArticleText>
            <ArticleText>
                Year by year, this gap between thought and action grows
                dangerously thin, with much thanks to technology.
            </ArticleText>
            <ArticleText>
                5 years ago, the COVID pandemic ignited an unprecedented push
                towards a digital society.
            </ArticleText>
            <ArticleText>But what does "digital" mean, anyway?</ArticleText>
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
