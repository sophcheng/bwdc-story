<script>
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div class="notice-container">
    <div style="z-index: 1; width: 100dvw;">
        <ArticleText color="lightblue">
            <em>Please view on a desktop or larger screen!<br /></em>
        </ArticleText>
    </div>
    <img src="postcardShot.png" alt="Backdrop of a city and riverfront view." />
</div>

<style>
    .notice-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100dvh;
        width: 100dvw;
        border-radius: 50px;
        position: relative;
    }

    .notice-container img {
        position: fixed;
        z-index: 0;
        left: 0;
        height: 100dvh;
    }
</style>
