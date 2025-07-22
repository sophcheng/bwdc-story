<div class="car-window">
    <div class="window-container"></div>

    <div class="panes">
        <div class="dashboard">
            <div class="backboard"></div>
        </div>
        <div class="blackboard"></div>

        <div class="steering-wheel"></div>
    </div>
    <img
        class="dashboard-view"
        src="cityViewBars.png"
        alt="City view from car dashboard"
    />
</div>
<div class="left-pane"></div>

<div class="right-pane"></div>

<style>
    .steering-wheel {
        border-style: outset;
        border-radius: 200px;
        width: 300px;
        height: 300px;
        border-width: 50px;
        border-color: white;
        background-color: #2f5249;
        position: absolute;
        z-index: 1;
        top: 550px;
        left: 200px;
        box-shadow:
            0 4px 8px 0 rgba(0, 0, 0, 0.2),
            0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }

    .car-window {
        background-color: #f4f7f6;
        position: relative;
    }

    .window-container {
        position: absolute;
        right: 100px;
        z-index: 2;
    }

    .dashboard,
    .blackboard {
        background-color: #597d4b;
        border-radius: 200px 200px 0 0;
        width: 1000px;
        margin-left: -10px;
        height: 300px;
        position: absolute;
        z-index: 1;
        top: 500px;
    }
    .blackboard {
        background-color: #97b067;
        left: 500px;
        z-index: -1;
        border-style: double none none none;
        border-width: 15px;
        border-color: pink;
    }
    .backboard {
        height: 200px;
        border-radius: 300px 300px 0 0;
        background-color: #97b067;
        opacity: 0.5;
    }
    .dashboard-view {
        position: absolute;
        z-index: 0;
        width: 100%;
        margin-top: -30px;
    }

    .left-pane,
    .right-pane {
        width: 700px;
        height: 390px;
        background-color: #2f5249;
        box-shadow:
            0 4px 8px 0 rgba(0, 0, 0, 0.2),
            0 6px 20px 0 rgba(0, 0, 0, 0.19);
        border-style: double;
        border-width: 15px;
    }

    .left-pane {
        transform: rotate(60deg);
        transform-origin: 0 0;
        margin-top: -100px;
        background-color: #1d312b;
        border-color: #97b067;
    }
    .right-pane {
        transform: rotate(-60deg);
        transform-origin: 30% 0;
        margin-left: 1000px;
        margin-top: 100px;
        border-radius: 50px;
        border-color: #1d312b;
    }
    .panes {
        display: flex;
        flex-direction: row;
    }
</style>
