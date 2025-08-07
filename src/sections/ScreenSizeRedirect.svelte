<script>
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div class="notice-container">
    <ArticleText color="lightblue">
        <em>Please view on a desktop or larger screen!<br /></em>
    </ArticleText>

    <!-- <ArticleText color="lightblue">sadf</ArticleText> -->
</div>

<style>
    .notice-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background-image: url("postcardShot.png");
        height: 100dvh;
        width: 100dvw;
        border-radius: 50px;
    }
</style>
