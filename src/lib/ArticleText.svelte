<script>
    let { children, color } = $props();
</script>

<div class="article">
    <div class="header" style="background-color: {color}">
        <button class="reddot"></button>
        <button class="yellowdot"></button>
        <button class="greendot"></button>
    </div>
    <p>
        {@render children()}
    </p>
</div>

<style>
    .header {
        display: flex;
        height: 40px;
        background-color: #3086cc;
        border-radius: 25px 25px 0 0;
        align-items: center;
        /* border-style: outset outset none none; */
    }
    .article {
        margin: 15vh auto;
        font-size: x-large;
        width: 60%;
        background-color: #f0ecd9;
        color: #873512;
        border: solid white 3px;
        border-radius: 25px;
        padding: 0 0 20px 0px;
        box-shadow: 16px 16px #8aa6df;
    }
    p {
        padding: 0 20px;
    }
    .reddot,
    .yellowdot,
    .greendot {
        width: 20px;
        height: 20px;
        border-radius: 25px;
        border-width: 0px;
        opacity: 0.8;
        margin: 5px;
    }

    .reddot {
        background-color: red;
        margin-left: 20px;
    }
</style>
